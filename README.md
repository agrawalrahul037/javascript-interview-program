# javascript-interview-program

### Table of Contents

| No. | Questions |
| --- | --------- |
|   | **important interview programs** |
|1  | [String sorting?](#String-sorting) |
|2  | [Sort Object of employee based on salary basis?](#Sort-Object-of-employee-based-on-salary-basis) |
|3  | [remove duplicate object from array?](#remove-duplicate-object-from-array) |
|4  | [check number is prime or not?](#check-number-is-prime-or-not) |
|5  | [list of prime number between 1 to 100?](#list-of-prime-number-between-1-to-100) |
|6  | [Swap two numbers without using third variable?](#Swap-two-numbers-without-using-third-variable) |
|7  | [method 1: make first letter uppercase of every word of any string?](#method-1-make-first-letter-uppercase-of-every-word-of-any-string) |
|7.1| [method 2: make first letter uppercase of every word of any string?](#method-2-make-first-letter-uppercase-of-every-word-of-any-string) |

1. ### String sorting

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

2. ### Sort Object of employee based on salary basis

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
3. ### remove duplicate object from array[while you know the property name]

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

4. ### check number is prime or not
    ### , it will return true if number is prime
```javascript
function primeN(num){
  let prime = (num===1)?false:true;
  for(let i=2;i<num;i++){
    if(num%i===0){
      prime = false
    }
  }
  return prime;
}
console.log(primeN(7));
```

5. ### list of prime number between 1 to 100

```javascript
let finalArray = [];
function primeN(){
  for(let i=2;i<100;i++){
    let prime = true;
    for(let j=2;j<i;j++){
      if(i%j===0){
         prime = false
      }
    }
    if(prime){
      finalArray.push(i)
    }
  }
  return finalArray;
}
console.log(primeN());
```
6. ### Swap two numbers without using third variable
```javascript
let a = 10;
let b = 20;

a = a+b;
b = a-b;
a = a-b;

console.log(a);
console.log(b);
```
7. ### method 1: make first letter uppercase of every word of any string

```javascript
let str = "my name is rahul";
let newStr = "";
let spaceIndex;
//newStr = newStr.concat(str[0].toUpperCase());
newStr = newStr + str[0].toUpperCase();         //without using concat method
for(let i=1;i<str.length;i++){
   if(str[i]=== " "){
     spaceIndex = i;
   }
   if(i === spaceIndex+1)
     newStr = newStr.concat(str[i].toUpperCase());
   else
     newStr = newStr.concat(str[i]);
}
console.log(newStr)
```
