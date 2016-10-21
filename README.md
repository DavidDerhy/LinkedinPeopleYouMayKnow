# LinkedinPeopleYouMayKnow
Script to connect automatically with all people you may know on Likedin

Go on the people you may know page : https://www.linkedin.com/people/pymk/hub 

Open Console : Ctrl + Alt + j

Copy & Past this Javascript code into the console : 

var window_height = document.body.clientHeight;
function scrollDown(height){
 scroll(0, document.body.clientHeight);
 setTimeout(function(){
  if(window_height != height){
   window_height = document.body.clientHeight;
   scrollDown(document.body.clientHeight);
  }else
      sendRequest();
      setTimeout(function(){
     scroll(0, 0);
        scrollDown(document.body.clientHeight);
      }, 2500); 
 
     }, 2500);
}
function sendRequest(){
  $("li.card button.bt-request-buffed").each(function(index) {
    $(this).click();
    console.log('Clicked');
    console.log($(this).attr('title'));
  });
}
scrollDown(window_height);

