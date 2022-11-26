1.  Explain, in your own words, the 2 things resource interfaces can be used for (we went over both in today's content)
	1. It can be used to restrict access to a resource or a strict, so only certain things are available
	2. It can be used to specify some requirements to be implemented
    
2.  Define your own contract. Make your own resource interface and a resource that implements the interface. Create 2 functions. In the 1st function, show an example of not restricting the type of the resource and accessing its content. In the 2nd function, show an example of restricting the type of the resource and NOT being able to access its content.
   
   ```
   pub contract Stuff {
   
	   pub resource interface ITest {
		   pub let age: Int
	   }
	   
	   pub resource Test: ITest {
		   pub let age: Int
		   pub let gender: String
		   
		   init() {
			   self.age = 22
			   self.gender = "male"
		   }
	   }
	   
	   pub fun noInterface() {
		   let test: @Test <- create Test()
		   log(test.gender) // "male"
		   
		   destroy test
	   }
	   
	   pub fun yesInterface() {
		   let test: @Test{ITest} <- create Test()
		   log(test.gender) // ERROR
		   
		   destroy test
		   
	   }
   }
```
    
3.  How would we fix this code?
   
   ```
   pub contract Stuff {

    pub struct interface ITest {
      pub var greeting: String
      pub var favouriteFruit: String
    }

    // ERROR:
    // `structure Stuff.Test does not conform 
    // to structure interface Stuff.ITest`
    pub struct Test: ITest {
      pub var greeting: String

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting // returns the new greeting
      }

      init() {
        self.greeting = "Hello!"
      }
    }

    pub fun fixThis() {
      let test: Test{ITest} = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!") // ERROR HERE: `member of restricted type is not accessible: changeGreeting`
      log(newGreeting)
    }
}
```

```
pub contract Stuff {

	// add the function to the interface
    pub struct interface ITest {
      pub var greeting: String
      pub var favouriteFruit: String
      
      pub fun changeGreeting(newGreeting: String): String
    }

    // Add the favouriteFruit to the struct and init()
    pub struct Test: ITest {
      pub var greeting: String
      pub var favouriteFruit: String

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting 
      }

      init() {
        self.greeting = "Hello!"
        self.favouriteFruit = "Banana"
      }
    }

    pub fun fixThis() {
      let test: Test{ITest} = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!") 
      log(newGreeting)
    }
}
```