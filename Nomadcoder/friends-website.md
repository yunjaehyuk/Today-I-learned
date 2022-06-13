# friends-website
status-bar box  
screen-header box
friends-display-link box
friends-screen__channel
user-component box

## friends-display-link box 

HTML
```
 <a id="friends-display-link">
      <i class="fa-solid fa-circle-info"></i> Friends'Names Display
      <i class="fa-solid fa-chevron-right fa-xs"></i>
 </a>
```

CSS
```
#friends-display-link {
  text-align: center;
  display: block;
  background-color: #fafafa;
  padding: 15px 0px;
  font-size: 16px;
  margin-bottom: 10px;
  margin-top: -15px;
}

#friends-display-link i {
  color: rgba(0, 0, 0, 0.3);
}
```
## friends-screen
HTML
```
 <div class="user-component">
        <div class="user-component__column">
        <img src="https://avatars.githubusercontent.com/u/77560753?v=4" class="user-component__avatar user-component__avatar--xl">
        <div class="user-component__text">
          
          <h4 class="user-component__title">Nicolas</h4>
          <!-- <h6 class="user-component__subtitle">This is whatever</h6> -->
          
        </div>
       </div>
      
       </div>
 <div class="friends-screen__channel">
         <div class="friends-screen__channel-header">
            <span>Channel</span>
            <i class="fa-solid fa-chevron-up fa-xs"></i>
         </div>
     <div class="user-component">
       <div class="user-component__column">
        <img src="https://avatars.githubusercontent.com/u/77560753?v=4" class="user-component__avatar user-component__avatar--sm">
        <div class="user-component__text">
        
        <h4 class="user-component__title user-component__title--not-bold">Channel</h4>
        <!-- <h6 class="user-component__subtitle">This is whatever</h6> -->
        
        </div>
       </div>
        <div class="user-component__column">
             <span>2</span>   
        <i class="fa-solid fa-chevron-right fa-xs"></i>
  
        </div>
 </div>
```
CSS
```
.user-component {
  justify-content: space-between;
  margin: 0px 25px;
  margin-bottom: 30px;
}

.user-component,
.user-component__column:first-child {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.user-component__avatar {
  width: 70px;
  height: 70px;
  border-radius: 27px;
  margin-right: 20px;
}
.user-component__title {
  font-weight: 600;
  font-size: 20px;
}
.user-component__subtitle {
  margin-top: 8px;
  font-size: 15px;
  color: rgba(0, 0, 0, 0.5);
}
.user-component__avatar--sm {
  width: 60px;
  height: 60px;
  border-radius: 25px;
}
.user-component__text span i {
  color: tomato;
}
.user-component__title {
  margin-bottom: 8px;
}

.friends-screen {
  padding: 0px var(--horizontal-space);
}

.friends-screen__channel-header {
  display: flex;
  padding: 20px 0px;
  justify-content: space-between;
  font-weight: 100;
  color
```













