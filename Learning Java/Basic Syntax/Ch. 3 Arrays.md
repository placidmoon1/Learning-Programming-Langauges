# Chapter 3: Arrays

### Declaring an array:

```Java
public class LearningArrays {
	public static void main(String args[]) {
		int[] arr1 = new int[dim]; //declaring a 1D array with dimension of dim
		int[] arr2 = {series of array literals corresponding to the type of array}; 
		int[][] arr3 = new int[dim1][dim2]; //declaring a 2D array with dimension of dim1 * dim2. 
		int[][] arr4 = {{1,2,3},{4,5,6}}; //declaring array with literals 
		//arrays aren't actually multidimensional, instead they are arrays within arrays. 
    }
} 
```

### Length of an array:

```Java
public class ArrayLength {
	public static void main(String args[]) { 
		String[] arr5 = new String[dim]; //1D array of index 0 ~ dim - 1
		len = arr5.length; //length is found by the .length property of array
		System.out.println(len); 
	}
}
```

### for-each (Enhanced for) loop:

```Java 
public class ForEachLoop {
	public static void main(String args[]) {
		int[] arr6 = {2,3,5,7};  
		for (int num:arr6) {
			System.out.println(num); //prints all elements of the array
		}
	}
}
```
