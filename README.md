# feb-2025-avasjcript-events-and-basic-interactivity
Event Name	Description
click	Fired when an element is clicked.
mouseover	Triggered when the mouse enters an element.
mouseout	Triggered when the mouse leaves an element.
keydown	Fires when a key is pressed.
keyup	Fires when a key is released.
change	Fires when an input field’s value changes.
submit	Triggers when a form is submitted.
load	Fires when a page or an image has loaded.


ADDING EVENT TO LISTENERS addEventListener()

<button id="myButton">Click Me</button>

<script>
  document.getElementById("myButton").addEventListener("click", function() {
    alert("Button clicked!");
  });
</script>

TO PREVENT DEFAULT BEHAVIOUR event.preventDefault().
EXAMPLE
<form id="myForm">
  <input type="text" placeholder="Enter something">
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById("myForm").addEventListener("submit", function(event) {
    event.preventDefault(); // Stops the form from submitting
    alert("Form submission prevented!");
  });
</script>

Event Delegation
Example
<div id="buttonContainer">
  <button class="btn">Button 1</button>
  <button class="btn">Button 2</button>
  <button class="btn">Button 3</button>
</div>

<script>
  document.getElementById("buttonContainer").addEventListener("click", function(event) {
    if (event.target.classList.contains("btn")) {
      alert(event.target.textContent + " clicked!");
    }
  });
</script>


Keyboard Events (Detecting Key Presses) 
Example
<input type="text" id="textInput" placeholder="Type something">

<script>
  document.getElementById("textInput").addEventListener("keydown", function(event) {
    console.log("Key pressed:", event.key);
  });
</script>


Mouse Events (Hover, Click, and More)
Example

<div id="hoverBox" style="width: 200px; height: 100px; background: lightgray;">Hover over me</div>

<script>
  const box = document.getElementById("hoverBox");

  box.addEventListener("mouseover", function() {
    box.style.backgroundColor = "lightblue";
  });

  box.addEventListener("mouseout", function() {
    box.style.backgroundColor = "lightgray";
  });
</script>

Toggle Password Visibility
Example
<input type="password" id="password">
<button onclick="togglePassword()">Show/Hide</button>

<script>
  function togglePassword() {
    const password = document.getElementById("password");
    password.type = password.type === "password" ? "text" : "password";
  }
</script>


Handling Modals (Popup Windows)
Example
<div id="modal" style="display: none; background: rgba(0,0,0,0.8); padding: 20px; color: white;">
  <p>This is a modal!</p>
  <button onclick="closeModal()">Close</button>
</div>
<button onclick="openModal()">Open Modal</button>

<script>
  function openModal() {
    document.getElementById("modal").style.display = "block";
  }

  function closeModal() {
    document.getElementById("modal").style.display = "none";
  }
</script>

<div id="modal" style="display: none; background: rgba(0,0,0,0.8); padding: 20px; color: white;">
  <p>This is a modal!</p>
  <button onclick="closeModal()">Close</button>
</div>
<button onclick="openModal()">Open Modal</button>

<script>
  function openModal() {
    document.getElementById("modal").style.display = "block";
  }

  function closeModal() {
    document.getElementById("modal").style.display = "none";
  }
</script>

Timers & Delayed Execution
Example
setTimeout(function() {
  alert("Hello after 3 seconds!");
}, 3000);

Example: repeate after every 2 seconds
let count = 0;
const interval = setInterval(function() {
  count++;
  console.log("Count:", count);
  if (count === 5) clearInterval(interval); // Stop after 5 times
}, 2000);

Removing Event Listeners
Example
function sayHello() {
  alert("Hello!");
}

const button = document.getElementById("myButton");
button.addEventListener("click", sayHello);

// Remove event listener after 5 seconds
setTimeout(() => {
  button.removeEventListener("click", sayHello);
}, 5000);
