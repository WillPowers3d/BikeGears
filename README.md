# BikeGears

Desktop calculator for bicycle **gear inches**. Pick a drivetrain, chainring, and cassette; the app reports the low-to-high range.

A Will + Cole app (Cole Stewart, `@colestew`), started during Code in Place.

## What it does

`BikeGearTkinter.py` opens a Tkinter window titled **Bicycle Gear Ratio Visualizer**. Three dropdowns choose:

| Control | Options |
| --- | --- |
| Brand | Rotor 1x, SRAM 1x Gravel, SRAM 2x Road, Shimano 1x Gravel, Shimano 2x Road |
| Chainring | Tooth counts for that brand (1x singles or 2x pairs such as 50-34) |
| Cassette | Named ranges such as 11-28 or 10-50 |

**Compute Gear Inch** prints `Your gear inch are {low} to {high}` (one decimal place).

Low uses the smallest chainring and largest cog; high uses the largest chainring and smallest cog:

```text
gear inches = 25 × (chainring teeth / cassette teeth)
```

`25` is the `WHEEL_SIZE` constant in the script (a stand-in for wheel diameter in inches).

## Tech stack

- Python 3
- [tkinter](https://docs.python.org/3/library/tkinter.html) (standard library)

No third-party packages and no `requirements.txt`. A display is required (this is a GUI, not a CLI).

## Run it

```bash
python3 BikeGearTkinter.py
```

## Example

Shimano 2x Road, 50-34 chainring, 11-28 cassette:

| End | Calculation | Result |
| --- | --- | --- |
| Low | `25 × (34 / 28)` | 30.4 |
| High | `25 × (50 / 11)` | 113.6 |

The label reads: `Your gear inch are 30.4 to 113.6`.

## License

MIT. See [LICENSE](LICENSE).
