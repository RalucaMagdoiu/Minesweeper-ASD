# Minesweeper-ASD

>This is a minesweeper game implemented in **C++** using data structures such as : **AVL Trees** ( for sorting strings in alphabetical order ) and **simple linked list** ( for storing and printing strings from a .txt file ).                                                                              
>It uses a **vector of vectors** to create two game borads( one that will not be visible for the user, in which mines are placed on the board, and a second visible one, in which the user selects cells ).



 [![MIT license](https://img.shields.io/badge/license-MIT-blue.svg)](https://badges.mit-license.org/)
 [![NrOfPageVisits](http://hits.dwyl.io/RalucaMagdoiu/Minesweeper-ASD.svg)](http://hits.dwyl.io/RalucaMagdoiu/Minesweeper-ASD)
 
---

# Table of Contents 
* ### Console Example
* ### Installation
* ### Code Examples
* ### License

---

# Console Example

![Alt Text](http://g.recordit.co/N4m0v2mQSR.gif)

---

# Installation

There are no Prerequisites for this project as long as you have a **C++ compatible IDE**.


#### Clone this repo to your local machine using  https://github.com/RalucaMagdoiu/Minesweeper-ASD

---

# Code Examples


```C++

struct ConsoleLimits       //a struct for the limits of the console window in which the cursor can move on the board
{   int left_x_limit,      //horizonatl x coordinate on which the cursor can move(left)
         right_x_limit,    //horizonatl x coordinate on which the cursor can move(right)
         up_y_limit,       //vertical y coordinate on which the cursor can move(up)
         down_y_limit;     //vertical y coordinate on which the cursor can move(down)
} console_limits;

```
```C++

struct GameData
{
    int no_of_rows,    //nr of board rows that are shown
        no_of_cols,    //nr of board columns that are shown
        no_of_mines,   //nr of mines on the board
        x_pos,         //x coordinate of where the cursor starts in the console window
        y_pos;         //y coordinate of where the cursor starts in the console window
    static const int mine_symbol = 0; //the symbol used for mines is "0"

} game_date;

```
```C++

void show_board(vector <vector <int> >& board, bool show_mines) //this function shows the visible board in the console and the user can move the cursor from cell to cell using W,A,S,D,w,a,s,d. 
{
    char ch = 178;        //the character used for showing the cells of the board is character 178 in ASCII code
    game_date.x_pos = 10;
    game_date.y_pos = 3;
    ...}

```
[ASCII code](http://www.theasciicode.com.ar/extended-ascii-code/graphic-character-high-density-dotted-ascii-code-178.html)

```C++

switch (level)          //this switch in the set_level function represents the levels of difficulty
    {case 1:                         // 9x9 board with 10 mines
        {game_date.no_of_rows = 9;
            game_date.no_of_cols = 9;
            game_date.no_of_mines = 10;
            SetConsoleTitle("MINE SWEEPER GAME -> EASY MODE");
            system("MODE 100, 40");
        }break;
    case 2:                        // 15x15 board with 30 mines
        {game_date.no_of_rows = 15;
            game_date.no_of_cols = 15;
            game_date.no_of_mines = 30;
            SetConsoleTitle("MINE SWEEPER GAME -> MEDIUM MODE");
            system("MODE 100, 40");
        }break;
    case 3:                        // 20x20 board with 50 mines(hardcore minesweeper)
           {game_date.no_of_rows = 20;
            game_date.no_of_cols = 20;
            game_date.no_of_mines = 50;
            SetConsoleTitle("MINE SWEEPER GAME -> HARD MODE");
            system("MODE 100, 50");
        }break;
        
```
 ```C++

 void save_score(const int& score)    //saves the user name and the score they made in a .txt file in 'Player:NAME,score:SCORE' format
{
    ofstream file;
    file.open("scores.txt", ios::app);
    string name;
    cin.ignore();
    do
    { cout << "\tENTER YOUR NAME\n>>> ";
      getline(cin, name);
    }
    while (name.length() == 0);
    file <<"Player:"<<name<<","<<"score:"<<score<<endl;
    cout<< endl;
    file.close();
}
 
 ```
![Alt Text](http://g.recordit.co/ev4IiTjDIY.gif)

```C++

struct AVLNode     //the AVL struct that stores the strings from the file as nodes and sorts them alphabetically
{
    string Name;
    int Balance;
    AVLNode *LeftChild;
    AVLNode *RightChild;
};
...
```
![Alt Text](http://g.recordit.co/rAee1Df1qx.gif)
---

# License

* **[MIT license](https://opensource.org/licenses/mit-license.php "MIT license")** 
* Click the link above or see the LICENSE.md file for details

