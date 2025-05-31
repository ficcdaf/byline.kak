# kak-byline

Expand and shrink line-based selections with <kbd>x</kbd> and <kbd>X</kbd>.

TL;DR: <kbd>x</kbd> drags the cursor down, <kbd>X</kbd> drags the cursor up. See
the "Examples" section below for a more detailed explanation.

Forked from [byline.kak](https://github.com/evanrelf/byline.kak). This fork
features a 17x performance increase per invocation.

## Installation

Add the `byline.kak` file to your `autoload/` directory using your preferred
method (manual download or plugin manager). Then, import the module in `kakrc`:

```kak
require-module byline
```

## Usage

The plugin doesn't map anything by default. The following examples assume you
have mapped `byline-drag-up` to `X` and `byline-drag-down` to `x`:

```kak
map global normal x ": byline-drag-down<ret>"
map global normal X ": byline-drag-up<ret>"
```

Use <kbd>x</kbd> and <kbd>X</kbd> to drag the cursor down and up by lines,
respectively. This expands or contracts your selection by lines, based on the
direction of your selection.

## Examples

#### Press <kbd>x</kbd> to drag the cursor (`|`) down

<table>

<tr>
<th>&nbsp;</th>
<th>&bull; Initial selection</th>
<th>&rarr; Pressed <kbd>x</kbd></th>
<th>&rarr; Pressed <kbd>x</kbd></th>
</tr>

<tr>

<td>Expand downwards</td>

<td>

```
[T|he quick brown
fox jumps over
the lazy dog
```

</td>

<td>

```
[The quick brown|
fox jumps over
the lazy dog
```

</td>

<td>

```
[The quick brown
fox jumps over|
the lazy dog
```

</td>

</tr>
</table>

<table>

<tr>
<th>&nbsp;</th>
<th>&bull; Initial selection</th>
<th>&rarr; Pressed <kbd>x</kbd></th>
<th>&rarr; Pressed <kbd>x</kbd></th>
</tr>

<tr>

<td>Contract downwards</td>

<td>

```
|The quick brown
fox jumps over
the lazy dog]
```

</td>

<td>

```
The quick brown
|fox jumps over
the lazy dog]
```

</td>

<td>

```
The quick brown
fox jumps over
|the lazy dog]
```

</td>

</tr>
</table>

#### Press <kbd><a-;></kbd> to swap the cursor (`|`) with the anchor (`[` or `]`)

<table>

<tr>
<th>&bull; Initial selection</th>
<th>&rarr; Pressed <kbd>&lt;a-;&gt;</kbd></th>
<th>&rarr; Pressed <kbd>&lt;a-;&gt;</kbd></th>
</tr>

<tr>

<td>

```
[The quick brown|
fox jumps over
the lazy dog
```

</td>

<td>

```
|The quick brown]
fox jumps over
the lazy dog
```

</td>

<td>

```
[The quick brown|
fox jumps over
the lazy dog
```

</td>

</tr>
</table>

#### Press <kbd>X</kbd> to drag the cursor (`|`) up

<table>

<tr>
<th>&nbsp;</th>
<th>&bull; Initial selection</th>
<th>&rarr; Pressed <kbd>X</kbd></th>
<th>&rarr; Pressed <kbd>X</kbd></th>
</tr>

<tr>

<td>Expand upwards</td>

<td>

```
The quick brown
fox jumps over
|the lazy dog]
```

</td>

<td>

```
The quick brown
|fox jumps over
the lazy dog]
```

</td>

<td>

```
|The quick brown
fox jumps over
the lazy dog]
```

</td>

</tr>
</table>

<table>

<tr>
<th>&nbsp;</th>
<th>&bull; Initial selection</th>
<th>&rarr; Pressed <kbd>X</kbd></th>
<th>&rarr; Pressed <kbd>X</kbd></th>
</tr>

<tr>

<td>Contract upwards</td>

<td>

```
[The quick brown
fox jumps over
the lazy dog|
```

</td>

<td>

```
[The quick brown
fox jumps over|
the lazy dog
```

</td>

<td>

```
[The quick brown|
fox jumps over
the lazy dog
```

</td>

</tr>
</table>
