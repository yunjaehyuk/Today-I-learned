# Find-webpag.md
status-bar box  
screen-header box  
icon-row box  
recommended-friends box  
open-chat box  
find-post box  

## recommended-friends box
HTML
```
<div class="recommended-friends">
        <h6 class="recommended-friends__title">Recommended Friends</h6>
        <span>You have no recommended-friends</span>
</div>
```
CSS
```
.recommended-friends {
  margin: 25px 0px;
  padding: 25px 0px;
  border-top: var(--main-border);
  border-bottom: var(--main-border);
}
.recommended-friends__title {
  font-size: 15px;
  color: rgba(0, 0, 0, 0.5);
}
.recommended-friends span {
  display: block;
  margin: 110px 0px;
  text-align: center;
}
```
## open-chat box
HTML
```
<div class="open-chat">
      <h4>Open chat</h4>
      <span class="open-chat__text"> Go to Openchat Home 
        <i class="fa-solid fa-chevron-right fa-xs"></i>
      </span>
    </div>
```
CSS
```
.open-chat {
  display: flex;
  justify-content: space-between;
}
.open-chat h4 {
  color: rgba(0, 0, 0, 0.5);
}
.open-chat span {
  color: rgba(0, 0, 0, 0.3);
}
```

## find-post box
HTML
```
<div class="find-post">
      <div class="find-column">
        <h2 class="find-post__title">#BTS</h2>
        <span class="find-post__text">#bts#army#friends</span>
        <div class="find-post__members">
          <img src="screenshots/iu blueming.jpg"/>
          <span>802 members |</span>
          <span class="find-post__active">Active</span>
        </div>
      </div>
      <div class="find-column">
        <div class="find-post__photo">
          <img src="screenshots/iu 마음.jpg"/>
          <div class="find-post__heart">
            <i class="fa-solid fa-heart fa-xs"></i>
          <span>326</span>
          </div>  
        </div>     
      </div>
```
CSS
```
find-post {
  align-items: center;
  display: flex;
  justify-content: space-between;
  margin-top: 12px;
}
.find-post__title {
  font-weight: 600;
  font-size: 20px;
  margin-bottom: 5px;
}
.find-post__text {
  margin-bottom: 5px;
  opacity: 0.6;
  text-transform: uppercase;
}
.find-post__members {
  margin-top: 5px;
}
.find-post__members img {
  width: 16px;
  height: 16px;
  border-radius: 5px;
}
.find-post__active {
  color: pink;
}
.find-post__photo {
  position: relative;
}
.find-post__photo img {
  width: 120px;
  height: 120px;
  border-radius: 10px;
}
.find-post__heart {
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 3px 8px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  position: absolute;
  bottom: 10px;
  right: 15px;
  font-size: 13px;
}
.find-post__heart span {
  margin-left: 3px;
  font-size: 15px;
}

```
