# The-mystery-of-8-queens-
This describe the game 8 queens, it's symbolism and how to achieve this on a chessboard 
Now, I'm sure you'll be wondering what "8 queens" mean? it's a game where you place 8 queens on a chessboard and they don't "kill" each other 
Now if you're familiar with chess, you'll know that the queen is the most OP character on the board. it can move like every other piece on the chessboard except the galloping cheat hehe (the knight). so then if this piece is so powerful, how can you place 8 of them so they don't actually kill each other?
firstly let's look at the why behind it. why play 8 queens? it's a game that shows wit, mathematical prowess and adaptive intelligence. it helped in combinatory maths and computational intelligence. 
so how do you place them across the board without them attacking each other? 
Firstly you place the first Queen in A7 , second queen in B3 third queen in c1 , then D6 , E8, F3, G4, H5
and viola you've placed 8 queens across the board without killing each other. 
here's a python script helping you explain how to solve the code 



def print_solution(board):
    for row in board:
        print(" ".join("Q" if x else "." for x in row))
    print()

def is_safe(board, row, col):
    for i in range(col):
        if board[row][i]:
            return False
    for i, j in zip(range(row, -1, -1), range(col, -1, -1)):
        if board[i][j]:
            return False
    for i, j in zip(range(row, len(board), 1), range(col, -1, -1)):
        if board[i][j]:
            return False
    return True

def solve(board, col):
    if col >= len(board):
        print_solution(board)
        return True
    res = False
    for i in range(len(board)):
        if is_safe(board, i, col):
            board[i][col] = 1
            res = solve(board, col + 1) or res
            board[i][col] = 0
    return res

N = 8
board = [[0]*N for _ in range(N)]
solve(board, 0)

I'll attach an image to show what the solved puzzle is like.
