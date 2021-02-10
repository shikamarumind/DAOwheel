# DAOwheel

@payable
@external
def bet(self, MONKEY: int, SLOTH: int, JAGUAR: int, TOUCAN: int, IGUANA: int, FROG: int, TIGER: int, user_seed: str = '') -> None:
- Monkey, Sloth, Jaguar, Toucan, and Iguana are main bets. Each of these can have a bet ranging 0.1 ICX to 100 ICX.
- Frog and Tiger are side bets. You can only bet 1 ICX on each specific side bet.
- The sum of all bets must be in the range of 0.1 ICX to 100 ICX.

@external
def bonus_spin(self, user_seed: str = '') -> None:
- Can only be triggered if player receives a "FROG" or "TIGER" bonus spin.

@external(readonly=True)
def check_bonus(self, wallet_address: str) -> str:
- Input wallet address, and in return receive a string of "FROG", "TIGER", or "NONE" for which bonus the player currently has.

@eventlog(indexed=1)
def SpinResult(self, result: str):
- Returns the result of the spin for both regular wheel and bonus wheel.

@eventlog(indexed=1)
def TotalPayoutAmount(self, payout: str):
- Returns the amount paid out to the player.


