# rentomojo
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Mocking and stubbing in frontend development</title>
</head>
<body>
<div>
    <button id="fetch-btn">FETCH</button>
</div>
</body>
</html>
const button = document.getElementById("fetch-btn");

button.addEventListener("click", function() {
  fetch("/api/users/")
    .then(response => {
      if (!response.ok) throw Error(response.statusText);
      return response.json();
    })
    .then(json => buildList(json));
});


function httpGetAsync(url, callback) {
  var xmlHttp = new XMLHttpRequest();
  xmlHttp.onreadystatechange = function() {
    if (xmlHttp.readyState == 4 && xmlHttp.status == 200)
      callback(xmlHttp.responseText);
  };
  xmlHttp.open('GET', url, true);
  xmlHttp.send(null);
}
