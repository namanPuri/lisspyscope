# lisspyscope

Generate **endlessly looping** stereo tones whose X-Y trace on an oscilloscope forms classic Lissajous figures.
```
pip install lisspyscope # minimal install
pip install lisspyscope[plot] # add matplotlib for on-screen plots
```
## Quick start
```
import lisspyscope as ls

#Hear and see a perfect circle (ratio 1 : 1, phase 90 °); press Ctrl-C to stop audio.

ls.play_lissajous()
```
Plot a 3 : 2 figure without sound
ls.plot_lissajous(base_freq=300, ratio=2, phase_deg=0)

| Parameter   | Purpose                                                   | Default |
|-------------|-----------------------------------------------------------|---------|
| `base_freq` | Left/X-channel frequency \(f_x\) in hertz                 | 1000     |
| `ratio`     | Integer multiplier for right/Y \(f_y = \text{ratio} \times f_x\) | 1 |
| `phase_deg` | Phase offset applied to \(f_y\) (degrees)                 | 90      |
| `sr`        | Sample rate (samples/s)                                   | 48,000  |

The library auto-selects the shortest duration that closes the figure, then **streams it in a loop** through a persistent audio stream so the scope trace stays rock-steady.

## Classroom ideas

- **Harmonic ratios** – vary `ratio` (1 : 2, 2 : 3, 3 : 4…) to visualise consonance and dissonance.  
- **Unknown-frequency measurement** – feed an external tone into one scope channel and tune `base_freq` until the figure simplifies, revealing the unknown frequency.

---

## License

MIT — see `LICENSE` for details.
