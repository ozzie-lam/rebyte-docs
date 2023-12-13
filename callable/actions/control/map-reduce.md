# Map Reduce

Map over an array and executes a sequence of actions in parallel. This is useful for doing multiple actions in parallel, such as scraping multiple web pages in parallel.

**Spec:**

* **MapOver:** Reference of an action name that outputs an array
* **Repeat:** Integer value that specifies the maximum iteration count
  * If repeat is not specified, then the iteration will stop when the array is exhausted. There is a hard limit of **64** iterations.
  * If repeat is specified, then the iteration will stop when the array is exhausted or the iteration count reaches the repeat value, whichever comes first.

**Config:**

* None

**Output**

* Each action inside map-reduce action will output **an array** of values.

**Example**

* [Map Reduce Example](https://rebyte.ai/p/21b2295005587a5375d8/callable/e5fc53ba2e8af8507418)

**Error Handling**

* MapOver must refer an action that outputs a non-empty array.
