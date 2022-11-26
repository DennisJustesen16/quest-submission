1.  In words, list 3 reasons why structs are different from resources.
	1. Structs can be copied.
	2. Structs can be overwritten.
	3. Structs can be created whenever we want them to.
    
2.  Describe a situation where a resource might be better to use than a struct.
	1. It would be used when dealing with valued stuff, since it cant just be copied
    
3.  What is the keyword to make a new resource?
	1. The keyword would be `create`
    
4.  Can a resource be created in a script or transaction (assuming there isn't a public function to create one)?
	1. A resource can only be created in a contract
    
5.  What is the type of the resource below?
    
	`pub resource Jacob {
	`
	`}
	1. Jacob

6.  Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them.
	
	```
	pub contract Test {

		    // Hint: There's nothing wrong here ;)
		    pub resource Jacob {
			pub let rocks: Bool
			init() {
			    self.rocks = true
			}
		    }

		    pub fun createJacob(): Jacob { // there is 1 here
			let myJacob = Jacob() // there are 2 here
			return myJacob // there is 1 here
		    }
	}
	```
		
	1. The first mistake is that there is no @ at the return type
	2. The second mistake is that an `=` operator is used. This should be a `<-` move operator
	3. The third mistake is that the keyword `create` is missing
	4. The fourth mistake is that the `<-` move operator is missing in the return statement
