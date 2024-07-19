# NumberGuess

 ```javascript
<script>
    const randNumber = parseInt(Math.random()*100)+1;
    let i = 0;
    let allGuesseNumbers = [];
    let guesses = document.querySelector("#guesses");
    console.log(randNumber);
    let numberform = document.querySelector("form");
    let result = document.querySelector("#result");
    numberform.addEventListener("submit", (e) =>{
    e.preventDefault();
    let selectedNumber = document.getElementById("selectedNumber").value;
    let submit = document.querySelector("#submit");
    if(selectedNumber > 99 || selectedNumber <= 0 || selectedNumber ==""){
     alert("Please select a b/t from 1 - 99");
    }else{
        i++;
        allGuesseNumbers.push(selectedNumber);
    if(randNumber === parseInt(selectedNumber)){
        result.innerHTML = "<h2>You are right, You Won the game</h2>";
        result.style.color = "Green";
    }else{
        result.innerHTML = "<h2>You are wrong, Better luck next time</h2>";
        result.style.color = "red";
    }
}

// button disabled after 5 click
if(i == 5){
submit.disabled = true;
guesses.innerHTML = `<span>Your Guesses: ${allGuesseNumbers.join()}</span>`;
let resetBtn = document.createElement("button");
resetBtn.textContent = "RESET GAME";
resetBtn.setAttribute("class","resetBtn")
guesses.appendChild(resetBtn);
resetBtn.addEventListener("click",() =>{
    window.location.reload()
})
}


})

</script>
