# Phaser.Scorebar

An attempt to create a simple and customizable scorebar for Phaser.js games.
Inspired by:
[phaser.healthbar](https://github.com/bmarwane/phaser.healthbar)

## Usage

### 1 - Import HealthBar file
Download script from github:
[click here](https://raw.githubusercontent.com/DeV1doR/phaser.scorebar/master/ScoreBar.js)
next just include the ScoreBar.js in the html file.
example : 
``` html
<script src="path/to/ScoreBar.js"></script>
```

### 2 - create a healthBar :

in the game/state create function instantiate a Healthbar like this: 

```javascript
create: function() {  
  var barConfig = {x: 200, y: 100};
  this.myHealthBar = new HealthBar(this.game, barConfig);
}
```
## Configuration

![](https://raw.githubusercontent.com/DeV1doR/phaser.scorebar/master/phaser.scorebar.png)

- **width**
- **height**
- **x:** initial x position 
- **y:** initial y position
- **R:** initial radius of cell box
- **color:**
- ****border:** border color
- ****rect:** color of cell rectange
- **margin:**
- ****x:** offset on x axe
- ****y:** offset on y axe
- **scale:** scale of scoreboard
- **label:** top label name of scoreboard
- **fixToCamera:** fix scoreboard to camera

this is the default configuration : 
```javascript
{
    R: 10,
    x: 30,
    y: 20,
    margin: {
        x: 0,
        y: 22
    },
    width: 210,
    height: 16,
    color: {
        border: 0x000000,
        rect: 0x1E90FF
    },
    scale: 1,
    label: "Scoreboard",
    fixToCamera: true,
};
```

## Methods

### setPercent(value):

set the width of the bar to the passed percentage value.
 
### redraw(dataArr): 
 redraw existing cells and add || remove another

**example:**

```javascript
 this.scoreBoard = new ScoreBoard(this.game);

 var dataArr = ["vaxXxa - 4.17k", "DeV1doR - 2.405k"];

 // this will create new two cells and fill with such data
 this.scoreBoard.redraw(dataArr);

 dataArr = ["vaxXxa - 4.17k", "DeV1doR - 2.405k", "Nick - 1.23k"];

 // this will redraw existing cells which already exists and creatae new one
 this.scoreBoard.redraw(dataArr);

 dataArr = ["vaxXxa - 4.17k"];

 // this will redraw first cell and remove other
 this.scoreBoard.redraw(dataArr); 
 ```

### draw(dataArr): 
 draw new cells by given array of strings

**example:**

```javascript
 var dataArr = ["vaxXxa - 4.17k", "DeV1doR - 2.405k"];

 // create two new cells
 scoreBoard.draw(dataArr);

 // or

 // if single one
 scoreBoard.draw("vaxXxa - 4.17k");
 ```

### setFixedToCamera(fixedToCamera):
  change camera fixing (default true)

### show():
  show scoreboard

### hide():
  hide scoreboard

### destroy():
  destroy current scoreboard
