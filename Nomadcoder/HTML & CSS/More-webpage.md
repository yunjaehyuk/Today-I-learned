# more website   
status-bar box 
screen-header box
user-component box
icon box
Suggestions box
## screen-header box
html
```
<header class="screen-header">
       <h1 class="screen-header__title">More</h1>
      <div class="screen-header__icons">
       <span><i class="fa-solid fa-magnifying-glass fa-lg"></i></span>
       <span><i class="fa-solid fa-music fa-lg"></i></span>
       <a href="setting.html">
       <span><i class="fa-solid fa-gear fa-lg"></i></span>
       </a>
       <span class="point"></span>
      </div>
</header>
```
CSS
```
.screen-header {
  display: flex;
  justify-content: space-between;
  padding: 25px;
  align-items: center;
}
.screen-header__title {
  font-size: 24px;
  font-weight: 800;
}
.screen-header__icons span {
  margin-left: 25px;
}
```
## user-component box
HTML
```
<div class="user-component">
        <div class="user-component__column">
          <img
            src="https://avatars.githubusercontent.com/u/77560753?v=4"
            class="user-component__avatar user-component__avatar--xl"
          />
          <div class="user-component__text">
            <h3 class="user-component__title">Nicolas</h3>
            <span class="user-component__content">
              +1 787-493-4219 <i class="fa-solid fa-circle-exclamation"></i></span>
          </div>
        </div>
        <div class="user-component__column">
          <div><i class="fa-solid fa-message fa-2x"></i></div>
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

```
## icon box
HTML
```
.icon-row {
  display: flex;
  flex-wrap: wrap;
}

.icon-row__icon {
  width: 25%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 20px;
}
.icon-row__icon i {
  font-size: 35px;
}
.icon-row__icon span {
  margin-top: 15px;
}
```
CSS
```
<div class="icon-row">
        <div class="icon-row__icon">
            <i class="fa-solid fa-calendar-days"></i>
            <span>Calendar</span>
        </div>
        <div class="icon-row__icon">
            <i class="fa-solid fa-download">
            </i>
            <span>Talk Drive</span>
        </div>
        <div class="icon-row__icon">
            <i class="fa-solid fa-face-grin"></i>
            <span>Emoticons</span>
        </div>
        <div class="icon-row__icon">
            <i class="fa-solid fa-brush"></i>
            <span>Themes</span>
        </div>
        <div class="icon-row__icon">
            <i class="fa-solid fa-wallet"></i>
            <span>Wallet</span>
        </div>
        <div class="icon-row__icon">
            <i class="fa-solid fa-comments"></i>
            <span>Openchat</span>
        </div>
    </div>
```
## Suggestion box 
HTML
```
<div class="more-suggestions">
        <h4 class="more-suggestions__title">Suggestions</h4>
        <div class="more-suggestions__icons">
         <div class="more-suggestions__icon">
          <div class="more-suggestions__icon-image">
            <i class="fa-solid fa-quote-right"></i>
          </div>
          <span class="more-suggestions__icon-text">Kokoa Story</span>
         </div>
         <div class="more-suggestions__icon">
          <div class="more-suggestions__icon-image">
            <i class="fa-solid fa-quote-right"></i>
          </div>
          <span class="more-suggestions__icon-text">Kokoa Story</span>
         </div>

        </div>
        </div>
       </div>
```
CSS
```
.more-suggestions {
  margin-top: 50px;
  border-top: var(--main-border);
  padding-top: 40px;
}
.more-suggestions__title {
  margin-bottom: 30px;
}
.more-suggestions__icons {
  display: flex;
}
.more-suggestions__icon {
  flex-direction: column;
  display: flex;
  align-items: center;
  margin-right: 30px;
}
.more-suggestions__icon-image {
  width: 60px;
  height: 60px;
  background-color: var(--yellow);
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 10px;
}
.more-suggestions__icon-image i {
  font-size: 32px;
  color: white;
}

```
