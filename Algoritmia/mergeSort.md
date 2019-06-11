# Merge Sort
```javascript
const mergeSort = (arr) =>{
  if(arr.length <= 1) return arr;
  const middle = arr.length / 2 ;
  const left = arr.slice(0, middle);
  const right = arr.slice(middle, arr.length);
  return merge(mergeSort(left), mergeSort(right));
}

const merge = (left, right) => {
  var result = [];
  while(left.length || right.length) {
    if(left.length && right.length) {
      if(left[0] < right[0]) {
        result.push(left.shift())
      } else {
        result.push(right.shift())
      }
    } else if(left.length) {
        result.push(left.shift())
      } else {
        result.push(right.shift())
      }
    }
  return result;
}
```