# Jakob-
I want to create a vocabulary app for myself and for that i want some functions like showing a cool fact above the country if the answer was correct. 
This is the code. 



let dictionary = JSON.parse(localStorage.getItem('dictionary')) || {};
let randomGermanWord;

function addVocabulary() {
    dictionary[germanText.value] = italianText.value;

    germanText.value = '';
    italianText.value = '';

    localStorage.setItem('dictionary', JSON.stringify(dictionary));
    render();
}

function render() {
    vocabularyList.innerHTML = '';
    for (let key in dictionary) {
        vocabularyList.innerHTML += `<li>${key} - ${dictionary[key]}</li>`;
    }
}

function nextVocabulary(){
    let obj_keys = Object.keys(dictionary);
    randomGermanWord = obj_keys[Math.floor(Math.random() * obj_keys.length)];
    word.innerHTML = `${dictionary[randomGermanWord]}?`;
}

function compare(){
    if(germanText.value == randomGermanWord) {
        text.innerHTML = 'Richtig!'; 
    } else {
        text.innerHTML = 'Falsch!'; 
    }
    germanText.value = '';

    nextVocabulary();
}
