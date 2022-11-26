1.  Define your own contract that stores a dictionary of resources. Add a function to get a reference to one of the resources in the dictionary.
```
pub contract Test {

	pub var dictionaryOfItems: @{String: Item}
	
	pub resource Item {
		pub let valuta: String
		intit(_valuta: String) {
			self.valuta = _valuta
		}
	}
	
	pub fun getReference(key: String): &Item? {
		return self.dictionaryOfItems[key] as &Item?
	}
	
	init() {
		self.dictionaryOfItems <- {
			"EUR": <- create Item(_valuta: "10"),
			"DKK": <- create Item(_valuta: "74.50")
		}
	}
}

```
    
2.  Create a script that reads information from that resource using the reference from the function you defined in part 1.
```
import Test from 0x01

pub fun main(): String {
  let ref = Test.getReference(key: "EUR")
  return ref.valuta // returns "10"
}
```
    
3.  Explain, in your own words, why references can be useful in Cadence.
	1. References can be used to get information from resources, without having to move said resources.