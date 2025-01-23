def player(prev_play, opponent_history=[]):
    # Append the previous play of the opponent to their history
    if prev_play:
        opponent_history.append(prev_play)

    # If this is the first move, play Rock
    if not opponent_history:
        return "R"

    # Count the occurrences of each move by the opponent
    rock_count = opponent_history.count("R")
    paper_count = opponent_history.count("P")
    scissors_count = opponent_history.count("S")

    # Determine the opponent's most frequent move
    if rock_count > paper_count and rock_count > scissors_count:
        # Opponent plays Rock most often, play Paper to win
        return "P"
    elif paper_count > rock_count and paper_count > scissors_count:
        # Opponent plays Paper most often, play Scissors to win
        return "S"
    elif scissors_count > rock_count and scissors_count > paper_count:
        # Opponent plays Scissors most often, play Rock to win
        return "R"
    else:
        # If there's a tie or no clear favorite, play Rock
        return "R"

# Example usage:
# print(player("", []))  # First move, should return "R"
# print(player("R"))     # Opponent played Rock, should return "P"
# print(player("P"))     # Opponent played Paper, should return "S"
# print(player("S"))     # Opponent played Scissors, should return "R"
