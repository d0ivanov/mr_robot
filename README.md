# Втора задача

Създайте клас TicTacToeBoard който да моделира игра на морски шах
-----
[![Build Status](https://travis-ci.com/d0ivanov/mr_robot.svg?branch=master)](https://travis-ci.com/d0ivanov/mr_robot)

## Методи

Класът трябва да предефинира операторът `[ ]`<br />
за да могат координатите от играта да се достъпват като dict:

    >>> board = TicTacToeBoard()
    >>> board["A1"] = "X"
    >>> board["A2"] = "O"
    >>> board["B1"] = "X"
    >>> board["A2"]
    'O'
    >>> board["A1"]
    'X'

Класът трябва да предефинира метода `__str__()`:

    >>> board = TicTacToeBoard()
    >>> print(board)

      -------------
    3 |   |   |   |
      -------------
    2 |   |   |   |
      -------------
    1 |   |   |   |
      -------------
        A   B   C

    >>> board['B2'] = 'O'
    >>> board['C1'] = 'X'
    >>> print(board)

      -------------
    3 |   |   |   |
      -------------
    2 |   | O |   |
      -------------
    1 |   |   | X |
      -------------
        A   B   C

    >>>

Трябва да са дефинирани 4 изключения:

`InvalidMove` -- извиква се при опит за презаписване на поле на което вече е заето. Например:

    >>> board["A1"] = 'X'
    >>> board["A1"] = 'O'

`InvalidValue` -- извиква се при опит за записване на символ различен от `('X', 'O')`. Например:

    >>> board["B1"] = 'щ'
    >>> board["B2"] = "Банани с пижами"

`InvalidKey` -- извиква се при опит за писане на невалидни координати:

    >>> board["A51"] = 'X'
    >>> board["NARNIA"] = 'O'

`NotYourTurn` -- Не е твой ред!!1!

    >>> board["A1"] = 'O'
    >>> board["A2"] = 'O'

Класът трябва да има метод `game_status()` който връща състоянието на играта:

    >>> board = TicTacToeBoard()
    >>> board["A1"] = "X"
    >>> board.game_status()
    'Game in progress.'
    ...
    >>> board.game_status()
    'Draw!'
    ...
    >>> board.game_status()
    'X wins!'
    ...
    >>> board.game_status()
    'O wins!'
