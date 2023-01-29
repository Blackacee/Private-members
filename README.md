# Private-members
 
class Queue {
 constructor () { // - does generate a closure with each instantiation.
 const list = []; // - local state ("private member").
 this.enqueue = function (type) { // - privileged public method
 // accessing the local state
 list.push(type); // "writing" alike.
 return type;
 };
 this.dequeue = function () { // - privileged public method
 // accessing the local state
 return list.shift(); // "reading / writing" alike.
 };
 }
}
var q = new Queue; //
 //
q.enqueue(9); // ... first in ...
q.enqueue(8); //
q.enqueue(7); //
 //
console.log(q.dequeue()); // 9 ... first out.
console.log(q.dequeue()); // 8
console.log(q.dequeue()); // 7
console.log(q); // {}
console.log(Object.keys(q)); // ["enqueue","dequeue"]
