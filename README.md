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
### remove duplicate object from array[while you know the property name]

```javascript
const array = [
  { id: 1, name: "john" },
  { id: 1, name: "john" },
  { id: 2, name: "mony" },
  { id: 2, name: "tony" },
  { id: 3, name: "jac" },
  { id: 4, name: "tom" },
  { id: 4, name: "tom" },
  { id: 5, name: "tommy" },
  { id: 6, name: "jick" },
  { id: 6, name: "moni" },
];
let newArr = array.reduce((finalArr,current)=>{
    let tempOb = finalArr.find((item)=> item.id === current.id && item.name === current.name)
    if(tempOb){
      return finalArr;
    }else{
      return finalArr.concat(current)
    } 
},[])
console.log(newArr);
```
