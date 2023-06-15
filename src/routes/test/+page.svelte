<!-- App.svelte -->
<script>
	import { onMount } from 'svelte';

	let board = [
		['', '', ''],
		['', '', ''],
		['', '', '']
	];

	let currentPlayer = 'X';
	let winner = null;
	let message = '';

	function checkWin() {
		const winningCombinations = [
			// Rows
			[0, 1, 2],
			[3, 4, 5],
			[6, 7, 8],
			// Columns
			[0, 3, 6],
			[1, 4, 7],
			[2, 5, 8],
			// Diagonals
			[0, 4, 8],
			[2, 4, 6]
		];

		for (let i = 0; i < winningCombinations.length; i++) {
			const [a, b, c] = winningCombinations[i];
			if (
				board[Math.floor(a / 3)][a % 3] &&
				board[Math.floor(a / 3)][a % 3] === board[Math.floor(b / 3)][b % 3] &&
				board[Math.floor(a / 3)][a % 3] === board[Math.floor(c / 3)][c % 3]
			) {
				return board[Math.floor(a / 3)][a % 3];
			}
		}

		if (board.flat().every((cell) => cell !== '')) {
			return 'tie';
		}

		return null;
	}

	function makeMove(row, col) {
		if (winner || board[row][col] !== '') return;

		board[row][col] = currentPlayer;

		winner = checkWin();

		if (winner) {
			if (winner === 'tie') {
				message = "It's a tie!";
			} else {
				message = `Player ${winner} wins!`;
			}
		} else {
			currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
		}
	}

	onMount(() => {
		message = "Player X's turn";
	});
</script>

<main>
	<h1>Tic-Tac-Toe</h1>
	<p>{message}</p>
	<div class="board">
		{#each board as row, i}
			<div class="row" key={i}>
				{#each row as cell, j}
					<div class="cell" on:click={() => makeMove(i, j)}>{cell}</div>
				{/each}
			</div>
		{/each}
	</div>
</main>

<style>
	.board {
		display: flex;
		flex-direction: column;
	}

	.row {
		display: flex;
	}

	.cell {
		width: 50px;
		height: 50px;
		border: 1px solid black;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 24px;
		cursor: pointer;
	}
</style>
