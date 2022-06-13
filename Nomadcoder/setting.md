# setting
status-bar box
alt-header box
setting-list box
nav-bar box

## alt-header box
HTML
```
<header class="alt-header">
      <div class="alt-header__column">
        <i class="fas fa-angle-left fa-3x"></i>
      </div>
      <div class="alt-header__column">
        <h1 class="alt-header__title">Settings</h1>
      </div>
      <div class="alt-header__column">
        <span><i class="fas fa-search fa-lg"></i></span>
      </div>
    </header>
```
CSS
```
.alt-header {
  padding: var(--horizontal-space);
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.alt-header__column {
  width: 33%;
}
.alt-header__title {
  font-size: 25px;
  font-weight: 600;
}

.alt-header__column:first-child {
  margin-right: auto;
}
.alt-header__column:nth-child(2) {
  text-align: center;
}
.alt-header__column:last-child {
  margin-left: auto;
  display: flex;
  justify-content: flex-end;
}
```
## alt-screen-header 
HTML
```
<main class="main-screen">
      <ul class="setting-list">
        <li class="settings__setting">
          <div class="setting_"></div>
          <i class="fa-solid fa-bullhorn"></i>
          <span>Notices</span>
        </li>
        <li class="settings__setting">
          <i class="fa-solid fa-flask"></i>
          <span>Kokoa Lab</span>
        </li>
        <li class="settings__setting">
          <i class="fa-solid fa-circle-exclamation"></i>
          <span>Version</span>
        </li>
      </ul>
     </main>
```
CSS
```
.settings__setting {
  padding: 20px 0;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  font-size: 20px;
  display: flex;
  align-items: center;
}

.settings__setting i {
  opacity: 0.8;
  margin-right: 20px;
  font-size: 22px;
}

.settings__setting-column:last-child {
  opacity: 0.5;
}

```



















