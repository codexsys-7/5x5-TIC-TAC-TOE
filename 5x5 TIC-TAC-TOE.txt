#include<iostream>
#include<vector>

std::string board[25]={" "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "," "};
int player=1;
int position=0;

void introduction()
{
  std::cout<<"IF YOU ARE READY TO START THE GAME PRESS [ENTER] TO BEGIN:";
  std::cin.ignore();

  std::cout<<"\n";

  std::cout<<"~~~~~~~~~~~~~~~~~~~~~~"<<"\n";
  std::cout<<"WELCOME TO TIC-TAC-TOE"<<"\n";
  std::cout<<"~~~~~~~~~~~~~~~~~~~~~~"<<"\n";
  std::cout<<"\n";

  std::cout<<"PLAYER1 - X "<<"\n";
  std::cout<<"PLAYER2 - O "<<"\n";
  
  std::cout<<"\n";

  std::cout<<"TRICK YOUR BRAIN WITH 5x5 TIC-TAC-TOE"<<"\n";
  std::cout<<"\n";

  std::cout<<"  1  | 2   | 3   | 4   | 5   \n";
  std::cout<<"_____|_____|_____|_____|_____\n";
  std::cout<<"  6  | 7   | 8   | 9   | 10   \n";
  std::cout<<"_____|_____|_____|_____|_____\n";
  std::cout<<"  11 | 12  | 13  | 14  | 15  \n";
  std::cout<<"_____|_____|_____|_____|_____\n";
  std::cout<<"  16 | 17  | 18  | 19  | 20  \n";
  std::cout<<"_____|_____|_____|_____|_____\n";
  std::cout<<"  21 | 22  | 23  | 24  | 25  \n";
  std::cout<<"     |     |     |     |     \n";
  std::cout<<"\n";
}

bool is_winner()
{
  bool winner=false;
  //conditions for rows..
  if((board[0]==board[1]) && (board[1]==board[2]) && (board[2]==board[3]) && (board[3]==board[4]) && board[0]!=" ")
  {
    winner=true;
  }
  else if((board[0]==board[1]) && (board[1]==board[2]) && (board[2]==board[3]) && (board[3]!=board[4]) && board[0]!=" ")
  {
    winner=true;
  }
  else if((board[4]==board[3]) && (board[3]==board[2]) && (board[2]==board[1]) && (board[1]!=board[0]) && board[4]!=" ")
  {
    winner=true;
  }



//2 row

  else if((board[5]==board[6]) && (board[6]==board[7]) && (board[7]==board[8]) && (board[8]==board[9]) && board[5]!=" ")
  {
    winner=true;
  }

  else if((board[5]==board[6]) && (board[6]==board[7]) && (board[7]==board[8]) && (board[8]!=board[9]) && board[5]!=" ")
  {
    winner=true;
  }

  else if((board[9]==board[8]) && (board[8]==board[7]) && (board[7]==board[6]) && (board[6]!=board[5]) && board[9]!=" ")
  {
    winner=true;
  }



//3 row

  else if((board[10]==board[11]) && (board[11]==board[12]) && (board[12]==board[13]) && (board[13]==board[14]) && board[10]!=" ")
  {
    winner=true;
  }
  else if((board[10]==board[11]) && (board[11]==board[12]) && (board[12]==board[13]) && (board[13]!=board[14]) && board[10]!=" ")
  {
    winner=true;
  }
  else if((board[14]==board[13]) && (board[13]==board[12]) && (board[12]==board[11]) && (board[11]!=board[10]) && board[14]!=" ")
  {
    winner=true;
  }


//4 row
 
  else if((board[15]==board[16]) && (board[16]==board[17]) && (board[17]==board[18]) && (board[18]==board[19]) && board[15]!=" ")
  {
    winner=true;
  }
  else if((board[15]==board[16]) && (board[16]==board[17]) && (board[17]==board[18]) && (board[18]!=board[19]) && board[15]!=" ")
  {
    winner=true;
  }
  else if((board[19]==board[18]) && (board[18]==board[17]) && (board[17]==board[16]) && (board[16]!=board[15]) && board[19]!=" ")
  {
    winner=true;
  }


//5 row
  else if((board[20]==board[21]) && (board[21]==board[22]) && (board[22]==board[23]) && (board[23]==board[24]) && board[20]!=" ")
  {
    winner=true;
  }
  else if((board[20]==board[21]) && (board[21]==board[22]) && (board[22]==board[23]) && (board[23]!=board[24]) && board[20]!=" ")
  {
    winner=true;
  }
  else if((board[24]==board[23]) && (board[23]==board[22]) && (board[22]==board[21]) && (board[21]!=board[20]) && board[24]!=" ")
  {
    winner=true;
  }




  //condition for columns..
  else if((board[0]==board[5]) && (board[5]==board[10]) && (board[10]==board[15]) && (board[15]==board[20]) && board[0]!=" ")
  {
    winner=true;
  }
  else if((board[0]==board[5]) && (board[5]==board[10]) && (board[10]==board[15]) && (board[15]!=board[20]) && board[0]!=" ")
  {
    winner=true;
  }
  else if((board[20]==board[15]) && (board[15]==board[10]) && (board[10]==board[5]) && (board[5]!=board[0]) && board[20]!=" ")
  {
    winner=true;
  }


//2 column

  else if((board[1]==board[6]) && (board[6]==board[11]) && (board[11]==board[16]) && (board[16] == board[21]) && board[1]!= " ")
  {
    winner=true;
  }
  else if((board[1]==board[6]) && (board[6]==board[11]) && (board[11]==board[16]) && (board[16] != board[21]) && board[1]!= " ")
  {
    winner=true;
  }
  else if((board[21]==board[16]) && (board[16]==board[11]) && (board[11]==board[6]) && (board[6] != board[1]) && board[21]!= " ")
  {
    winner=true;
  }


//3 column

  else if((board[2]==board[7]) && (board[7]==board[12]) && (board[12]==board[17]) && (board[17] == board[22]) && board[2]!= " ")
  {
    winner=true;
  }
  else if((board[2]==board[7]) && (board[7]==board[12]) && (board[12]==board[17]) && (board[17] != board[22]) && board[2]!= " ")
  {
    winner=true;
  }
  else if((board[22]==board[17]) && (board[17]==board[12]) && (board[12]==board[7]) && (board[7] != board[2]) && board[22]!= " ")
  {
    winner=true;
  }


//4 column

  else if((board[3]==board[8]) && (board[8]==board[13]) && (board[13]==board[18]) && (board[18] == board[23]) && board[3]!= " ")
  {
    winner=true;  
  }
  else if((board[3]==board[8]) && (board[8]==board[13]) && (board[13]==board[18]) && (board[18] != board[23]) && board[3]!= " ")
  {
    winner=true;  
  }
  else if((board[23]==board[18]) && (board[18]==board[13]) && (board[13]==board[8]) && (board[8] != board[3]) && board[23]!= " ")
  {
    winner=true;  
  }


//5 column

  else if((board[4]==board[9]) && (board[9]==board[14]) && (board[14]==board[19]) && (board[19] == board[24]) && board[4]!= " ")
  {
    winner=true;  
  }
  else if((board[4]==board[9]) && (board[9]==board[14]) && (board[14]==board[19]) && (board[19] != board[24]) && board[4]!= " ")
  {
    winner=true;  
  }
  else if((board[24]==board[19]) && (board[19]==board[14]) && (board[14]==board[9]) && (board[9] != board[4]) && board[24]!= " ")
  {
    winner=true;  
  }



  //condition for daigonally.
  //[o] left to right
  else if((board[0]==board[6]) && (board[6]==board[12]) && (board[12]==board[18]) && (board[18] == board[24]) && board[0]!= " ")
  {
    winner=true;
  }
  else if((board[0]==board[6]) && (board[6]==board[12]) && (board[12]==board[18]) && (board[18] != board[24]) && board[0]!= " ")
  {
    winner=true;
  }
  else if((board[24]==board[18]) && (board[18]==board[12]) && (board[12]==board[6]) && (board[6] != board[0]) && board[24]!= " ")
  {
    winner=true;
  }


  //[1] left to right
  else if((board[1]==board[7]) && (board[7]==board[13]) && (board[13]==board[19]) && board[1]!= " ")
  {
    winner=true;
  }
  else if((board[19]==board[13]) && (board[13]==board[7]) && (board[7]==board[1]) && board[19]!= " ")
  {
    winner=true;
  }  

  //[5] left to right
  else if((board[5]==board[11]) && (board[11]==board[17]) && (board[17]==board[23]) && board[5]!= " ")
  {
    winner=true;
  }
  else if((board[23]==board[17]) && (board[17]==board[11]) && (board[11]==board[5]) && board[23]!= " ")
  {
    winner=true;
  }  
  

  //right to left diagonal
  else if((board[4]==board[8]) && (board[8]==board[12]) && (board[12]==board[16]) && (board[16] == board[20]) && board[4]!= " ")
  {
    winner=true;
  }
  else if((board[4]==board[8]) && (board[8]==board[12]) && (board[12]==board[16]) && (board[16] != board[20]) && board[4]!= " ")
  {
    winner=true;
  }
  else if((board[20]==board[16]) && (board[16]==board[12]) && (board[12]==board[8]) && (board[8]!=board[4]) && board[20]!=" ")
  {
    winner=true;
  }

  //[3] right to left
  else if((board[3]==board[7]) && (board[7]==board[11]) && (board[11]==board[15]) && board[3]!= " ")
  {
    winner=true;
  }
  else if((board[15]==board[11]) && (board[11]==board[7]) && (board[7]==board[3]) && board[15]!= " ")
  {
    winner=true;
  }

  //[9] right to left
  else if((board[9]==board[13]) && (board[13]==board[17]) && (board[17]==board[21]) && board[9]!= " ")
  {
    winner=true;
  }
  else if((board[21]==board[17]) && (board[17]==board[13]) && (board[13]==board[9]) && board[21]!= " ")
  {
    winner=true;
  }


  return winner;

}


//function to check whether the board is filled or not..
bool filled_up()
{
  bool filled=true;
  for(int i=0;i<25;i++)
  {
    if(board[i]==" ")
    {
      filled=false;
    }
  }
  return filled;
}


//this fucntion will keep track of the x/o entered by players..
void draw()
{
  std::cout<<"        1|        2|        3|        4|        5\n";
  
  std::cout<<board[0]<<"        |"<<board[1]<<"        |"<<board[2]<<"        |"<<board[3]<<"        |"<<board[4]<<"        "<<"\n";
  
  std::cout<<"_________|_________|_________|_________|_________\n";
  
  std::cout<<"        6|        7|        8|        9|       10\n";
  
  std::cout<<board[5]<<"        |"<<board[6]<<"        |"<<board[7]<<"        |"<<board[8]<<"        |"<<board[9]<<"        "<<"\n";
  
  std::cout<<"_________|_________|_________|_________|_________\n";
  
  std::cout<<"       11|       12|       13|       14|       15\n";
  
  std::cout<<board[10]<<"        |"<<board[11]<<"        |"<<board[12]<<"        |"<<board[13]<<"        |"<<board[14]<<"        "<<"\n";
  
  std::cout<<"_________|_________|_________|_________|_________\n";
  
  std::cout<<"       16|       17|       18|       19|       20\n";
  
  std::cout<<board[15]<<"        |"<<board[16]<<"        |"<<board[17]<<"        |"<<board[18]<<"        |"<<board[19]<<"        "<<"\n";
  
  std::cout<<"_________|_________|_________|_________|_________\n";
  
  std::cout<<"       21|       22|       23|       24|       25\n";
  
  std::cout<<board[20]<<"        |"<<board[21]<<"        |"<<board[22]<<"        |"<<board[23]<<"        |"<<board[24]<<"        "<<"\n";
  
  std::cout<<"         |         |         |         |         \n";
  std::cout<<"\n";

}

//this function allows to set the position for the player..

void set_position()
{
  std::cout<<"Player-"<<player<<" Enter Number Between[1-25]: ";
  while(!(std::cin>>position)) 
  //while condition executes when user enters number other than [1-25].
  {
    std::cout<<"Player-"<< player <<", Please Enter a Valid Number Between[1-25]: ";
    std::cin.clear();
    std::cin.ignore();
  }

  std::cout<<"\n";

  while(board[position-1]!=" ")
  {
    std::cout<<"OOps, The Place Is Already Filled By Some Other Number."<<"\n";
    std::cout<<"\n";
    std::cout<<"Player-"<<player<<"'s  Enter Number Between[1-25]: ";
    std::cin>>position;

    std::cout<<"\n";
  }
}


//updating the board..
void update_board()
{
  if(player % 2 == 1)
  {
    board[position-1]="X";
  }
  else
  {
    board[position-1]="O";
  }
}


//changing the player..
void change_player()
{
  if(player==1)
  {
    player++;
  }
  else
  {
    player--;
  }
}


//to take the turn..
void take_turn()
{
  while(!is_winner() && !filled_up())
  {
    set_position();
    update_board();
    change_player();
    draw();   
  }
}


//fucntion to end the game..
void end_game()
{
  if(is_winner())
  {
    std::cout<<"\n";
    std::cout<<"Hurrah! You Have Won The Match:"<<"\n";
  }
  else if(filled_up())
  {
    std::cout<<"\n";
    std::cout<<"OO Come On We Have A Tie."<<"\n";
  }
}


//main fucntion to call the fucntions..
int main()
{
  introduction();
  take_turn();
  end_game();
}