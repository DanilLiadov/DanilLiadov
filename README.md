- 👋 Hi, I’m @DanilLiadov
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
DanilLiadov/DanilLiadov is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

<!---
Code for Python:

def pretty_board(styler):
  styler.set_caption('Chessboard')
  return styler

import pandas as pd

def new_game(chess_board):
  a=['rw','pw','','','','','pb','rb']
  b=['kw','pw','','','','','pb','kb']
  c=['bw','pw','','','','','pb','bb']
  d=['qw','pw','','','','','pb','qb']
  e=['Lw','pw','','','','','pb','Vb']
  f=['bw','pw','','','','','pb','bb']
  g=['kw','pw','','','','','pb','kb']
  h=['rw','pw','','','','','pb','rb']
  chess_board=pd.DataFrame(data={'a':a,'b':b,'c':c,'d':d,'e':e,'f':f,'g':g,'h':h})
  return (chess_board)

import numpy as np
def view_board(chess_board):
  dfe=[]
  for i in range(4):
    dfe.append(['true ', 'false '])
    for j in range(3):
      dfe[2*i].extend(['true ', 'false '])
    dfe.append(['false ', 'true '])
    for j in range(3):
      dfe[2*i+1].extend(['false ', 'true '])

  scb = chess_board.style \
    .relabel_index([1,2,3,4,5,6,7,8],axis=0)
  scb.set_table_styles([
      {'selector': '.true', 'props': 'background-color: #ffe6e6;'},
      {'selector': '.false', 'props': 'background-color: #ffffff;'},
  ], overwrite=False)

  cell_color = pd.DataFrame(dfe,
                            index=chess_board.index,
                            columns=chess_board.columns[:8])
  scbnew=scb.set_td_classes(cell_color).pipe(pretty_board)
  return(scbnew)

sfe=pd.Series(range(8))
for i in range(len(sfe)):
  sfe[i]=bool(sfe[i]%2)
sfe=sfe.apply(lambda v: not v)
dfe=pd.DataFrame([[],[],[],[],[],[],[],[]])
for i in range(8):
  dfe[str(i)]=sfe
  sfe=sfe.apply(lambda v: not v)
display(dfe)

def main_game(chess_board,game_end):
  while not game_end:
    move=input()
    if move=='eg' or move=='endgame':
      game_end=True
    elif move=='vb' or move=='viewboard':
      display(view_board(chess_board))
    else:
      chess_board[move[-2]][int(move[-1])-1]=chess_board[move[0]][int(move[1])-1]
      chess_board[move[0]][int(move[1])-1]=''
    display(view_board(chess_board))
  return(game_end)

chess_board={}
chess_board=new_game(chess_board)
game_end=False
main_game(chess_board,game_end)
--->

