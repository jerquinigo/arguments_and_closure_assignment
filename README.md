# Exercises
Jonathan Erquinigo

1. Create two functions: `double` and `square`.
`double` should take a number and return the number times two.
`square` should take a number and return the number squared.

 * Create a third function `doubleSquare` that uses both of the functions to return a number that is first doubled and then squared.


 const double = (num) => {
   return num * num;
 }

 const square = (num) => {
   return num * num;
 }

 console.log(square(4))

 const doubleSquare = (num) => { // 9
   let  double1 = double(num) // 18
   let changedDouble = square(double1) // 3

   return changedDouble // 9
 }
 console.log(doubleSquare(9))


2. Create a function `classyGreeting` that takes as input the strings `firstName`  and `lastName`,
and returns a string with a greeting using the two.

  * Create a second function `yell`  that takes string as input and returns the string in all capitalized letters.
  * Create a third function  `yellGreeting`  that will take the `firstName`  and `lastName`  as inputs and yell a greeting using the two.

  const classyGreeting =(firstName,lastName) => {
      return `Hello ${firstName} ${lastName}`;
    };

  const yell = (allCaps) => {
    let str = allCaps;
    return str.toUpperCase();

   };
    //console.log(yell("hello"))

  const yellGreeting = (first,last) =>  {
    classyGreeting(first,last)
    return yell(classyGreeting(first,last));
  }
  console.log(yellGreeting("Jonathan","ta"));


3. The [concat](https://www.w3schools.com/jsreF/jsref_concat_array.asp) array method is used to merge two (or more) arrays.
Write a `removeDupes` function that takes an array as an argument and returns a copy without any duplicate elements.
Then, write a function `concatAndRemoveDupes`  that combines two arrays and removes any duplicates.
const removeDupes = (arr) => {
let empObj = {}
for(let i = 0; i < arr.length - 1; i++){
  if(empObj[arr[i]] === undefined){
    empObj[arr[i]] = arr[i];
  };

};
return empObj;
};

console.log(removeDupes([1,2,3,4]));

const concatAndRemoveDupes = (arr1,arr2) => {
let arrf1 = arr1
let arrf2 = arr2
let arrf3 = [...arrf1,...arrf2]
removeDupes(arrf3);

return removeDupes(arrf3);



  _Hint:_ Use the array method `includes`, an object, or a Set. Or the spread operator instead of concat.  

4. Given a list of grades, we can get the median grade by sorting the list and taking the middle element, or the average of the two middle elements.
Create the functions `sort` and `middleElement`, and then use them to create the functions `median`.

let grades = [91, 85, 100, 92, 88];

console.log(median(grades)); // Should log 91

const sort = (arr) => {
arr.sort(function(a, b){return a - b});
return arr
}
//console.log(sort([91,85,100,92,88]));

const middleElement = (arr) => {
let arrtest =arr[Math.floor(arr.length/2)]
console.log(arrtest);
return arrtest

}
//console.log(middleElement(0,1,2,3,4));
/*Create the functions `sort` and `middleElement`, and then use them to create the functions `median`.

let grades = [91, 85, 100, 92, 88];

console.log(median(grades)); // Should log 91*/
const median = (arr) => {
return middleElement(sort(arr))
}
console.log(median([91, 85, 100, 92, 88]));

5. Write a function called `repeat` that takes in a string and numberOfTimes. The function should log to the screen the string however
many times as numberOfTimes. If the user does not enter a numberOfTimes it should default to 2.

const repeat = (str1,numberOfTimes = 2) => {

  for(let i = 0;i <= numberOfTimes; i++){
    console.log (str1)
  }
}

  console.log(repeat("Hello",7))

6. Using the spread operator, write a function that can take any number of arguments and return the sum of all of them.

const spread = (...type) => {
  let sum = 0
let empArray = [];
  for(let i = 0; i < type.length; i++){
     console.log(sum = sum + type[i])
  }

}
console.log(spread(1,2,3,4,5,6,78,))


7. Write a function called `adder` takes in one number and returns a function that will add that number with another number.
Using `adder` create an `add5` and an `add9` function. Hint: Closures!


const adder = () => {
let num = 7;
  return function add5(){
    let num3 = num + 5
    return num3
  };

  return function add9(){
    let num5 = num + 9
    return num5
  };

};
let sumOf5 = adder(5)
let sumOf9 = adder(9)
let sum = adder()

console.log(sumOf5())
console.log(sumOf9())
console.log(sum())
