# Lab Report 3 - Symptoms and Failure-inducing Inputs
## Part 1
### Failure-inducing input for reverseInPlace():
```
@Test
  public void testReverseInPlaceFail() {
    int[] input1 = { 1, 2, 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3, 2, 1 }, input1);
	}
```
### Input that doesn't induce failure:
```
  @Test 
	public void testReverseInPlacePass() {
    int[] input1 = { 1, 2, 2, 1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1, 2, 2, 1 }, input1);
	}
```
### The symptom:
![Image](reversesymptom.png)
