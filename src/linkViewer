(function() {
  // container
  var container = document.createElement("div");
  container.id = "link-viewer";

  container.style.all = "unset";

  container.style.backgroundColor = "#FFF";
  container.style.width = "400px";
  container.style.border = "solid 1px #AAA";
  container.style.borderRadius = "2px";
  container.style.position = "fixed";
  container.style.top = "100px";
  container.style.left = "100px";
  container.style.zIndex = "9999999999999999999";

  // iFrame
  var iFrame = document.createElement("iframe");
  iFrame.id = "link-viewer-iframe";

  iFrame.style.all = "unset";

  iFrame.style.margin = "0px";
  iFrame.style.width = container.style.width;
  iFrame.height = iFrame.style.height = "200px";
  iFrame.style.border = "none";
  iFrame.src = "data:text/html, <h1 style='margin: 40px 0px 20px 0px; text-align: center; font-family: sans-serif;'>Enter a link to get started!</h1>";

  iFrame.style.resize = "both";
  iFrame.style.overflow = "hidden";

  // content holder
  var contentHolder = document.createElement("div");
  contentHolder.id = "link-viewer-content-holder";

  contentHolder.style.all = "unset";

  contentHolder.style.width = "400px";
  contentHolder.style.height = iFrame.height;
  contentHolder.style.padding = "0px";
  contentHolder.style.margin = "0px";

  contentHolder.append(iFrame);
  container.append(contentHolder);

  // header
  var header = document.createElement("div");
  header.id = "link-viewer-header";

  header.style.all = "unset";

  header.style.display = "flex";
  header.style.justifyContent = "space-between";
  header.style.alignItems = "center";
  header.style.userSelect = "none";
  header.style.padding = "3px";
  header.style.margin = "0px";
  header.style.borderBottom = "solid 1px #AAA";

  header.style.height = "20px";
  header.style.width = Number(contentHolder.style.width.slice(0, -2) - 6) + "px";

  var dragged = false;
  var startX = 0;
  var startY = 0;
  header.addEventListener("mousedown", function(event) {
    startX = Number(container.style.left.slice(0, -2)) - event.clientX;
    startY = Number(container.style.top.slice(0, -2)) - event.clientY;
    dragged = true;
  });
  header.addEventListener("mouseup", function(event) {
    dragged = false;
  });

  // Also keeping track of size too
  window.addEventListener("mousemove", function(event) {
    if (dragged) {
      container.style.top = (event.clientY + startY) + "px";
      container.style.left = (event.clientX + startX) + "px";
    }
    var x = Number(container.style.left.slice(0, -2));
    var y = Number(container.style.top.slice(0, -2));
    if (x < 0) {
      container.style.left = "0px";
    }
    if (y < 0) {
      container.style.top = "0px";
    }

    contentHolder.style.height = iFrame.style.height;
    contentHolder.style.width = iFrame.style.width;

    header.style.width = (Number(contentHolder.style.width.slice(0, -2)) - 6) + "px";

    container.style.width = contentHolder.style.width;
    container.style.height = (Number(contentHolder.style.height.slice(0, -2)) + 27) + "px";

    if(Number(header.style.width.slice(0, -2)) < 300){
    contentHolder.style.width = "300px";
    header.style.width = "294px";
    container.style.width = "300px";
    iFrame.style.width = "300px";
    }
  });

  // text stuff
  var headerTextHolder = document.createElement("div");

  headerTextHolder.style.all = "unset";

  // header text
  var headerText = document.createElement("h1");
  headerText.textContent = "Link Viewer";

  headerText.style.all = "unset";

  headerText.style.fontFamily = "sans-serif";
  headerText.style.color = "#444";
  headerText.style.fontSize = "20px";
  headerText.style.margin = "0px";
  headerText.style.padding = "0px";

  headerTextHolder.append(headerText);
  header.append(headerTextHolder);

  // button stuff 
  var headerButtonHolder = document.createElement("div");

  headerButtonHolder.style.all = "unset";

  // link button
  var lButton = document.createElement("button");
  lButton.textContent = "change link";

  lButton.style.all = "unset";

  lButton.style.fontFamily = "sans-serif";
  lButton.style.width = "100px";
  lButton.style.height = "20px";
  lButton.style.cursor = "pointer";
  lButton.style.margin = "0px 3px 0px 3px";
  lButton.style.color = "#333";
  lButton.style.border = "solid 1px #333";
  lButton.style.borderRadius = "2px";
  lButton.style.backgroundColor = "#EEE";
  lButton.style.textAlign = "center";

  lButton.addEventListener("mouseover", function(event) {
    lButton.style.backgroundColor = "#DDD";
  });
  lButton.addEventListener("mouseleave", function(event) {
    lButton.style.backgroundColor = "#EEE";
  });
  lButton.addEventListener("click", function(event) {
    var link = prompt("Enter link URL (Not all sites work)");
    if (!link) {
      return;
    }

    iFrame.src = link;
  });

  headerButtonHolder.append(lButton);

  // minimize button
  var mButton = document.createElement("button");
  mButton.textContent = "-";

  mButton.style.all = "unset";

  mButton.style.fontFamily = "sans-serif";
  mButton.style.width = "20px";
  mButton.style.height = "20px";
  mButton.style.cursor = "pointer";
  mButton.style.margin = "0px 3px 0px 3px";
  mButton.style.color = "#333";
  mButton.style.border = "solid 1px #333";
  mButton.style.borderRadius = "2px";
  mButton.style.backgroundColor = "#EEE";
  mButton.style.textAlign = "center";

  mButton.addEventListener("mouseover", function(event) {
    mButton.style.backgroundColor = "#DDD";
  });
  mButton.addEventListener("mouseleave", function(event) {
    mButton.style.backgroundColor = "#EEE";
  });
  mButton.addEventListener("click", function(event) {
    var closed = contentHolder.style.display === "none";
    if (closed) {
      contentHolder.style.display = "block";
      header.style.borderBottom = "solid 1px #AAA";
    } else {
      contentHolder.style.display = "none";
      header.style.borderBottom = "none";
    }
  });

  headerButtonHolder.append(mButton);

  // x button
  var xButton = document.createElement("button");
  xButton.textContent = "x";

  xButton.style.all = "unset";

  xButton.style.fontFamily = "sans-serif";
  xButton.style.width = "20px";
  xButton.style.height = "20px";
  xButton.style.cursor = "pointer";
  xButton.style.margin = "0px 3px 0px 3px";
  xButton.style.color = "#333";
  xButton.style.border = "solid 1px #333";
  xButton.style.borderRadius = "2px";
  xButton.style.backgroundColor = "#F33";
  xButton.style.textAlign = "center";

  xButton.addEventListener("mouseover", function(event) {
    xButton.style.backgroundColor = "#E22";
  });
  xButton.addEventListener("mouseleave", function(event) {
    xButton.style.backgroundColor = "#F33";
  });
  xButton.addEventListener("click", function(event) {
    container.remove();
  });

  headerButtonHolder.append(xButton);
  header.append(headerButtonHolder);

  contentHolder.before(header);

  // add to body
  document.body = document.body || document.createElement("body");
  document.body.append(container);
})();
