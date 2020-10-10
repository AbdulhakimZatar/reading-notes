# Node Ecosystem, TDD, CI/CD

## Review, Research, and Discussion

### Array map() Method
The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

### Array reduce() Method
The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in single output value.

### superagent()
SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!

#### superagent() using .then

```js
function getCharacters() {
  let URL = 'https://swapi.dev/api/people/'
  let obj = {}
  return superagent.get(URL).then((data) => {
    let result = data.body.results

    result.forEach((item) => {
      let name = item.name
      let url = item.url

      obj[`${name}`] = `${url}`
    })
    console.log(obj)
    return obj
  })
}
```
**log**
```
{
  'Luke Skywalker': 'http://swapi.dev/api/people/1/',
  'C-3PO': 'http://swapi.dev/api/people/2/',
  'R2-D2': 'http://swapi.dev/api/people/3/',
  'Darth Vader': 'http://swapi.dev/api/people/4/',
  'Leia Organa': 'http://swapi.dev/api/people/5/',
  'Owen Lars': 'http://swapi.dev/api/people/6/',
  'Beru Whitesun lars': 'http://swapi.dev/api/people/7/',
  'R5-D4': 'http://swapi.dev/api/people/8/',
  'Biggs Darklighter': 'http://swapi.dev/api/people/9/',
  'Obi-Wan Kenobi': 'http://swapi.dev/api/people/10/'
}
```

#### superagent() using async / await

```js
async function city(name){
  let cityName = name;
  URL = `https://geocode.xyz/${cityName}?json=1`
  let result = await superagent.get(URL)
  console.log(`Latitude: ${result.body.latt} | Longitude: ${result.body.longt}`)
}

city("amman")
```
**log**
```
Latitude: 31.95436 | Longitude: 35.90414
```


### Promises 
A promise in JavaScript is similar to a promise in real life. When we make a promise in real life, it is a guarantee that we are going to do something in the future. Because promises can only be made for the future.

#### Are all callback functions considered to be Asynchronous? Why or Why Not?
No. Only I/O is usually asynchronous, but many other callbacks are synchronous.

