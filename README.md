# Codewars

* My solved task's on the [codewars.com](https://www.codewars.com/users/konderev.ivan)

* Language: [JavaScript](https://en.wikipedia.org/wiki/JavaScript)

* Topic: [Algorithms](https://en.wikipedia.org/wiki/Algorithm)

---

### [For Twins: 2. Math operations](https://www.codewars.com/kata/59c287b16bddd291c700009a)

Prolog:

  This kata series was created for friends of mine who just started to learn programming. Wish you all the best and keep your mind open and sharp!

Task:

  A magician in the subway showed you a trick, he put an ice brick in a bottle to impress you.The bricks width and height are equal, forming a square. Just for fun and also to impress the magician and people around, you decided to calculate the brick's volume. Write a function iceBrickVolume that will accept these parameters:

    radius - bottle's radius (always > 0);
    bottleLength - total bottle length (always > 0);
    rimLength - length from bottle top to brick (always < bottleLength);
    And return volume of ice brick that magician managed to put into a bottle.

Note:

  All inputs are integers.

Examples:

  iceBrickVolume(1, 10, 2); // => 16
  iceBrickVolume(5, 30, 7); // => 1150

##### Solution:

```javascript
function iceBrickVolume(radius, bottleLength, rimLength) {
  return 2 * Math.pow(radius, 2) * (bottleLength - rimLength);
}
```
---

### [Holiday VI - Shark Pontoon](https://www.codewars.com/kata/57e921d8b36340f1fd000059)

Your friend invites you out to a cool floating pontoon around 1km off the beach. Among other things, the pontoon has a huge slide that drops you out right into the ocean, a small way from a set of stairs used to climb out.

As you plunge out of the slide into the water, you see a shark hovering in the darkness under the pontoon... Crap!

You need to work out if the shark will get to you before you can get to the pontoon. To make it easier... as you do the mental calculations in the water you either freeze when you realise you are dead, or swim when you realise you can make it!

You are given 5 variables: sharkDistance = distance the shark needs to cover to eat you in metres, sharkSpeed = how fast it can move in metres/second, pontoonDistance = how far you need to swim to safety in metres, youSpeed = how fast you can swim in metres/second, dolphin = a boolean, if true, you can half the swimming speed of the shark as the dolphin will attack it.

If you make it, return "Alive!", if not, return "Shark Bait!".

##### Solution:

```javascript
function shark(pontoonDistance, sharkDistance, youSpeed, sharkSpeed, dolphin){
  if (dolphin) {
    sharkSpeed /= 2;
  }
  if (pontoonDistance / youSpeed < sharkDistance / sharkSpeed) {
    return "Alive!";
  } else {
    return "Shark Bait!";
  }
}
```
---

### [Find the unique number](https://www.codewars.com/kata/585d7d5adb20cf33cb000235)

There is an array with some numbers. All numbers are equal except for one. Try to find it!
```javascript
findUniq([ 1, 1, 1, 2, 1, 1 ]) === 2
findUniq([ 0, 0, 0.55, 0, 0 ]) === 0.55
```
It’s guaranteed that array contains more than 3 numbers.

The tests contain some very huge arrays, so think about performance.

##### Solution:

```javascript
function findUniq(arr) {
  for (var i = 1; i <= arr.length; i++){
    if (arr[i - 1] != arr[i] && arr[i - 1] === arr[i + 1]){
      return arr[i];
    }
    if (arr[i - 1] != arr[i] && arr[i - 1] != arr[i + 1]){
      return arr[i - 1];
    }
    if (arr[i - 1] === arr [i] && arr[i - 1] != arr[i + 1]){
      return arr[i + 1];
    }
  } 
}
```
---

### [Who likes it?](https://www.codewars.com/kata/5266876b8f4bf2da9b000362)

You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.

Implement a function likes :: [String] -> String, which must take in input array, containing the names of people who like an item. It must return the display text as shown in the examples:

```javascript
likes [] // must be "no one likes this"
likes ["Peter"] // must be "Peter likes this"
likes ["Jacob", "Alex"] // must be "Jacob and Alex like this"
likes ["Max", "John", "Mark"] // must be "Max, John and Mark like this"
likes ["Alex", "Jacob", "Mark", "Max"] // must be "Alex, Jacob and 2 others like this"
```
For 4 or more names, the number in and 2 others simply increases.

##### Solution:

```javascript
function likes(names) {
  switch(names.length){
    case 0: return 'no one likes this';
    case 1: return names[0] + ' likes this';
    case 2: return names[0] + ' and ' + names[1] + ' like this';
    case 3: return names[0] + ', ' + names[1] + ' and ' + names[2] + ' like this';
    default:
    return names[0] + ', ' + names [1] + ' and ' + (names.length - 2) + ' others like this';
  }
}
```
---
