# SearchController
Easy-to-use search controllers, which keeps your entities inside him, without violating the principle of single responsibility
![alt text](preview.png)

### Examples

```swift
class Animal: Searchable {
	var parameter: String {
		return "\(name)\(age)"
	}
	
	var name: String
	var age: Int
	
	init(_ name: String, _ age: Int) {
		self.name = name
		self.age = age
	}
}

let arrayToFilter = [Animal("Cat", 3), Animal("Dog", 3), Animal("Duck", 3)]
let searchController = SearchController<Animal>.init(arrayToFilter, caseSensitive: false)


searchController.search(by: "cat3") // Animal("Cat, 3")

```
