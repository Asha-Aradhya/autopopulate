//---------SEARCH BAR LOCAL STORAGE------------

//---------PSEUDO CODE------------

//---------------------------------------------

//---------GETTING HTML ELEMENTS--------------------------------

const form = document.getElementById("form");
const searchBar = document.getElementById("search");
const submitButton = document.getElementById("submit");
const deleteButton = document.getElementById("delete");
const ul = document.getElementById("ul");
const resultsHTML = document.getElementById("results");
let recentSearches;
let allsearches_arr =
  localStorage.allsearches !== undefined
    ? JSON.parse(localStorage.allsearches)
    : [];

//---------CONDITIONS--------------------------------

if (localStorage.recentSearches && localStorage.recentSearches != "") {
  //?why repeating localStorage.recentSearches
  recentSearches = JSON.parse(localStorage.recentSearches); // if Local Storage is NOT empty collect  the words that the user typed
} else {
  recentSearches = []; //this will shows an empty array
}

//--------On typing text in the search bar

searchBar.oninput = function () {
  let results = [];
  const userInput = this.value.toLowerCase();
  resultsHTML.innerHTML = "";
  if (userInput.length > 0) {
    results = getResults(userInput);
    resultsHTML.style.display = "block";
    for (i = 0; i < results.length; i++) {
      resultsHTML.innerHTML += "<li>" + results[i] + "</li>";
    }
  }
};

//---------------Filter the data-------------

const getResults = (input) => {
  const results = [];
  for (i = 0; i < allsearches_arr.length; i++) {
    if (input === allsearches_arr[i].slice(0, input.length)) {
      results.push(allsearches_arr[i]);
    }
  }
  return results;
};

//---------FUNCTIONS--------------------------------
const makeListItem = (text, parent) => {
  //this function is creating a listItem variable by using createElement() it add another
  //instance to a list which ul is the parent.
  let listItem = document.createElement("li"); // this is creatign <li></li>
  listItem.textContent = text; // text comes from the array saved in Local Storage
  listItem.className = "list-group-item"; // this creating a class for the listItem
  parent.appendChild(listItem); // this add the word (listItem) in the ul
};

//---------WORKING WITH THE ARRAY recentSearches to create an ul--------
recentSearches.forEach((element) => {
  // this is collecting the element in the array in  the Local Storage
  makeListItem(element, ul); //this the call back to the function above
});

console.log("hi");
//---------FUNCTION to check a condition----------------
const isDuplicateValue = (arr, text) => {
  // this works because you need to see what the addEventListener is doing
  //arr is a variable created in line 73 it collect all the listItems
  for (let i = 0; i < arr.length; i++) {
    // this loop is going through the Local Storage array
    if (arr[i].toLowerCase() == text.toLowerCase()) {
      return true;
    }
  }
  return false;
};
console.log("hi");

const setDataToLocalStorage = (text) => {
  let items = localStorage.getItem("allsearches");
  allsearches_arr = [];
  if (items === null || items.length === 0) {
    // items is null, [] or '' (empty string)
    allsearches_arr.push(text.toLowerCase());
    localStorage.allsearches = JSON.stringify(allsearches_arr);
  } else {
    allsearches_arr = JSON.parse(localStorage.allsearches);
    allsearches_arr.push(text);
    localStorage.allsearches = JSON.stringify(allsearches_arr);
  }
};
//---------FUNCTION to check a condition----------------

form.addEventListener("submit", (event) => {
  //event built-in method keyword of EventListener
  event.preventDefault(); //? Prevent default behaivor on click
  if (
    searchBar.value == "" ||
    isDuplicateValue(allsearches_arr, searchBar.value)
  ) {
    return; //this means go back to the start from the top or get out
  } else {
    //this will add the new word in the input
    recentSearches.push(searchBar.value);
    makeListItem(searchBar.value, ul); //callback adding arguments the first parameter make a listitem from the input and put it inside the ul
    //localStorage.recentSearches = JSON.stringify(recentSearches) // the stingify function is to make a string JSON out of it
    setDataToLocalStorage(searchBar.value);
    searchBar.value = "";
  }
});

deleteButton.addEventListener("click", () => {
  localStorage.clear();
  recentSearches = [];
  allsearches_arr = [];
  searchBar.value = "";
  // I use querySelectorAll because it returns a static collection
  let arr = document.querySelectorAll("li");
  // I use the static collection for iteration
  for (let i = 0; i < arr.length; i++) {
    // this wil go throught all the li and delete them on the html page
    arr[i].remove();
  }
});
