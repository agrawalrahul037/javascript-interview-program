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
|1  | [method 2: make first letter uppercase of every word of any string?](#method-2-make-first-letter-uppercase-of-every-word-of-any-string) |
|2  | [method 3: make first letter uppercase of every word of any string?](#method-3-make-first-letter-uppercase-of-every-word-of-any-string) |
|8  | [simple promise program?](#simple-promise-program) |
|9  | [Inheritance in javascript ES5?](#Inheritance-in-javascript-ES5) |
|10  | [chunked array?](#chunked-array) |
|11  | [make own concat function?](#make-own-concat-function) |
|3  | [remove duplicate number from array?](#remove-duplicate-number-from-array) |

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
1. ### method 2: make first letter uppercase of every word of any string

```javascript
let str = "my name is rahul";
let newStr = "";
let splitedArray = str.split(" ");
for(let i=0;i<splitedArray.length;i++){
  let tempStr = splitedArray[i];
  for(let j=0;j<tempStr.length;j++){
    if(j===0)
     newStr = newStr + tempStr[j].toUpperCase(); 
    else
    newStr = newStr + tempStr[j];
  }
  newStr = newStr + " ";
}
console.log(newStr)
```
2. ### method 3: make first letter uppercase of every word of any string

```javascript
let str = 'my name is rahul';
let newStr = '';
for(let i=0;i<str.length;i++){
  if(str[i] == ' '){
    newStr+=str[i];
    i++;
    newStr+=str[i].toUpperCase();
  }
  else{
    if(i==0)
    newStr+=str[i].toUpperCase();
    else
    newStr+=str[i];
  }
}
console.log(newStr)
```
8. ### simple promise program

```javascript
let testPromise = new Promise((resolve,reject)=>{
  let age = 38;
  if(age<35)
  resolve("my age is less than 35")
  else
  reject("my age is greater than 35")
})
testPromise.then((success)=>{
  console.log(success)
}).catch((err)=>{
  console.log(err)
})
```
9. ### Inheritance in javascript ES5
```javascript
function parentC(){
  this.name = "I am parent function"
}
parentC.prototype.parentInnerFunc = function(){
  console.log("Inside parentInnerFunc")
}
function childC(){
  this.name = "I am child function";
  this.compName = "I am child Comp"
  parentC.call(this)
}

childC.prototype = Object.create(parentC.prototype)
let ob = new childC()
console.log(ob.name)
console.log(ob.compName)
ob.parentInnerFunc()
```
10. ### chunked array

```javascript
let arr = [3,4,5,6,7,8,9,2,10,15,4];
let chunkedArray = []
function chunkedArrayFunc(n){
  for(let i=0;i<arr.length;i+n){
    chunkedArray.push(arr.splice(i,n))
  }
  return chunkedArray;
}
console.log(chunkedArrayFunc(6)); // number of chunking
```

11. ### make own concat function

```javascript
function myConcat(){
    let newStr = "";
    for(let i=0;i<arguments.length;i++){
      newStr = newStr + arguments[i];
    }
  return newStr;
}
console.log(myConcat('abc','xyz','fds'))
```
12. ### remove duplicate number from array

```javascript
let arr = [1,4,7,1,5,4]
let newArr = []
for(let i=0;i<arr.length;i++){
  if(newArr.indexOf(arr[i])<0){
    newArr.push(arr[i])
  }
}
console.log(newArr)
```
