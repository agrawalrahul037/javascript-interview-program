# javascript-interview-program
important interview programs


### String sorting

```javascript
let str = "rahulagrawal";
let arr  = str.split('');
for(let i=0;i<arr.length;i++){
  for(let j=i+1;j<arr.length;j++){
  if(arr[i].charCodeAt(0)>arr[j].charCodeAt(0)){
    let temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
  }
  }
}
console.log(arr.join(""));
```

### Sort Object of employee based on salary basis

```javascript
const arr = [
  {id:"1",name:"rahul",salary:"5300"},
  {id:"1",name:"pankaj",salary:"3300"},
  {id:"1",name:"neeraj",salary:"6000"},
  {id:"1",name:"manoj",salary:"2100"},
]

for(let i=0;i<arr.length;i++){
  for(let j=i+1;j<arr.length;j++){
    if(arr[i].salary>arr[j].salary){
      let temp = arr[i];
      arr[i] = arr[j];
      arr[j] = temp;
    }
  }
}
console.log(arr);
```
