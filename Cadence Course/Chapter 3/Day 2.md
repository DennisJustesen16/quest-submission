1. Write your own smart contract that contains two state variables: an array of resources, and a dictionary of resources. Add functions to remove and add to each of them. They must be different from the examples above.
```flow
pub contract ShoppingCart {

	pub var arrayOfItems: @[Item]
	pub var dictionaryOfItems: @{String: Item}

	pub resource Item {
		pub let itemName: String
		init() {
			self.itemName = "Milk"
		}
	}
	
	pub fun addItemArray(item: @Item) {
		self.arrayOfItems.append(<- item)
	}
	
	pub fun removeItemArray(index: Int): @Item {
		return <- self.arrayOfItems.remove(at: index)
	}
	
	pub fun addItemDictionary(item: @Item) {
		let key = item.itemName
		self.dictionaryOfItems[key] <-! item
	}
	
	pub fun removeItemDictionary(key: String): @Item {
		let item <- self.dictionaryOfItems.remove(key: key) ?? panic("Could not find the item!")
		return <- item
	}

	init() {
		self.arrayOfItems <- []
		self.arrayOfItems <- {}
	}
}
```
