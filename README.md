## **Turing Challenge: twoSumLessThank using PHP**
<p>
Suppose we have an array A of integers and another integer K is given. We have to find the maximum S such that there exists i < j with A[i] + A[j] = S and S < K. If there is no i, j exists satisfying this equation, then return -1. 

**Example:**

```php
Input=** [34,23,1,24,75,33,54,8] 
``` 

**K= 60**

**Output= 58** 

Explanation:  the output will be 58, as we can use 34 and 24 to sum 58, which is less than 60. </p>

```php
class Solution{
	function twoSumLessThank($A, $K){
		$arr = array();
	    for($i = 0; $i < count($A); $i++) {
	        for ($j=1; $j < count($A); $j++) {                
	            if($i < $j){
	            	$S = $A[$i] + $A[$j];
	            	if($S < $K) array_push($arr, $S);
	            }	            
	        }
	    }
	    if(!empty($arr) && max($arr) < $K){
	    	return max($arr);
	    }else{
	    	return -1;
	    }
	}
}

$arr = [34,23,1,24,75,33,54,8];
$k = 60;
$solution = new Solution();
$output = $solution->twoSumLessThank($arr, $k);
print_r($output);
```
```php
Output: 58
```