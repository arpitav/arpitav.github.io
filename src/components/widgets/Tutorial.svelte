<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>how to play</h3>
<div>Guess the baby's name in {ROWS} tries!</div>
<div>Each guess must be a valid {COLS} letter name. Hit the enter button to submit.</div>
<div>
	After each guess, the color of the tiles will change to show how close your guess was to the
	name.
</div>
<div class:complete={visible} class="examples">
	<div><strong>Examples</strong></div>
	<div class="row">
		<Tile value="s" state="🟩" />
		<Tile value="w" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="m" state="🔳" />
		<Tile value="i" state="🔳" />
	</div>
	<div>The letter <strong>S</strong> is in the name and in the correct spot.</div>
	<div class="row">
		<Tile value="a" state="🔳" />
		<Tile value="r" state="🟨" />
		<Tile value="p" state="🔳" />
		<Tile value="i" state="🔳" />
		<Tile value="t" state="🔳" />
		<Tile value="a" state="🔳" />
	</div>
	<div>The letter <strong>R</strong> is in the name but in the wrong spot.</div>
	<div class="row">
		<Tile value="g" state="🔳" />
		<Tile value="a" state="🔳" />
		<Tile value="n" state="🔳" />
		<Tile value="e" state="⬛" />
		<Tile value="s" state="🔳" />
		<Tile value="h" state="🔳" />
	</div>
	<div>The letter <strong>E</strong> is not in the name in any spot.</div>
</div>
<div>
	This is a recreation of the original <a
		href="https://www.nytimes.com/games/wordle/"
		target="_blank"
		rel="noreferrer">Wordle</a
	>
	but more relavant to our lives.
	Forked from a repository by
	<a href="https://github.com/MikhaD" target="_blank" rel="noreferrer">MikhaD</a>.
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		border-bottom: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
</style>
