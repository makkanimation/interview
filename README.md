# interview

# Q1: Given an array of positive integers arr[] of size n, the task is to find third largest distinct element in the array.

> Note: If the third largest element does not exist, return -1.

```
function thirdLargest($arr) {
    $n = count($arr);
    if ($n < 3) {
        return "Array must have at least 3 elements.";
    }
 
    $first = $second = $third = PHP_INT_MIN;
 
    foreach ($arr as $num) {
        if ($num > $first) {
            $third = $second;
            $second = $first;
            $first = $num;
        } elseif ($num > $second) {
            $third = $second;
            $second = $num;
        } elseif ($num > $third) {
            $third = $num;
        }
    }
    return [$first,$second,$third];
}
$values = thirdLargest(["1","45","12","76"]);
if($values[1]==$values[2])
{
    echo "-1";
}
else{
    echo $values[2];
}

```

