import 'dart:io';

class game{
  Map<int,String>play_board={};
  
  void build_board(){
    for(int i=1;i<=9;i++){
      play_board[i]='';
    }
  }

  void print_board(){
  print(' ${play_board[1]} | ${play_board[2]} | ${play_board[3]} ');
  print('---------');
  print(' ${play_board[4]} | ${play_board[5]} | ${play_board[6]} ');
  print('---------');
  print(' ${play_board[7]} | ${play_board[8]} | ${play_board[9]} ');
  }

  void check_board(int position,String turn){
    while(play_board[position] !=''){
        print('sorry you cann\'t choose this position');
        stdout.write('choose other position : ');
        int p=int.parse(stdin.readLineSync()!);
        position = p;
    }
    play_board[position]=turn;
  }

  String check_winner(){
    // row
    for(int i=1;i<=9;i +=3){
      Set row={play_board[i],play_board[i+1],play_board[i+2]};
      if(row.length ==1 && play_board[i] !=''){
        return "${play_board[i]}\'s player is the Winner";
      }
    }
    // colum
    for(int i=1;i<=3;i++){
      Set colum={play_board[i],play_board[i+3],play_board[i+6]};
      if(colum.length ==1 && play_board[i] !=''){
        return "${play_board[i]}\'s player is the Winner";
      }
    }
    // diagonals
      Set dia1={play_board[1],play_board[5],play_board[9]};
      Set dia2={play_board[3],play_board[5],play_board[7]};
      if((dia1.length ==1 || dia2.length==1) && play_board[5] !=''){
        return "${play_board[5]}\'s player is the Winner";
    }
    // No Winner
    if(play_board.values.every((xo) => xo !='')){
      return "No Winner o_0";
    }
    return '0';
  }
}

void main(List<String> args) {
  stdout.write('choose X or O : ');
  String turn = stdin.readLineSync()!.toUpperCase();
  game xo = game();
  xo.build_board();

  while(xo.check_winner() =='0'){
    xo.print_board();
    stdout.write('Enter the position : ');
    int position = int.parse(stdin.readLineSync()!);
    xo.check_board(position, turn);
    turn = (turn == "X"? 'O':"X");    // change turn x to o and oppisit
  }
  xo.print_board();
  // who win ??
  print((xo.check_winner() != 'No Winner o_0'? xo.check_winner() :'Game Over : ${xo.check_winner()}'));
}
