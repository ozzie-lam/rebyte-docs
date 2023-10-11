# Map Reduce

Map over an array and executes a sequence of actions in parallel.

* **Spec:**
  * **Parameters:**

    * **MapOver:** Reference of an action name that outputs an array
    * **Repeat:** Integer value that specifies the maximum iteration count
      * If repeat is not specified, then the iteration will stop when the array is exhausted. There is a hard limit of **64** iterations.
      * If repeat is specified, then the iteration will stop when the array is exhausted or the iteration count reaches the repeat value, whichever comes first.

* **Config:**:
  *  None

**Output**

**Example**

**Error Handling**
  * MapOver must refer an action that outputs a non-empty array.