# sabahna-audio-lyric

`sabahna-audio-lyric` is a package that provides a simple and customizable way to highlight lyrics in sync with audio time for a music player website, especially for a karaoke system.

## Installation

You can install the package using `npm`:


## Usage

To use the `sabahna-audio-lyric` package, you need to pass three props and style props can be nullable to the `<LRC>` component:

- `lrcString`: A string containing the lyrics to be highlighted.
- `currentTime`: A number representing the current time of the audio being played.
- `audioStatus`: A boolean representing the audio played or paused.
- `style`: A object style representing the lyric Main BackgroundColor, Main TextColor, Main HighlightColor, Main FontSize,  Main FontWeight and Main FontFamily.

Here's an example usage of the `<LRC>` component:

```jsx
import { LRC } from 'sabahna-audio-lyric';

function MyMusicPlayer() {
  const [lyrics, setLyrics] = useState('[00:00.00]First line of lyrics\n[00:10.00]Second line of lyrics\n[00:20.00]Third line of lyrics');
  const playerRef = useRef(null);

  const style = {
    mainBackColor: '#000',
    mainTextColor: '#fff',
    mainHighlightColor: 'red',
    mainFontSize: '1.3em',
    mainFontWeight: '300',
    mainFontFamily: 'Verdana',
  }

  return (
    <>
      <audio ref={playerRef} src="/path/to/audio/file.mp3" />
      <LRC lrcString={lyrics} currentTime={playerRef?.current?.currentTime} audioStatus={audioStatus} style={style}  />
    </>
  );
}
```

## Props

### `lrcString` (required)

A string containing the lyrics to be highlighted. The lyrics must be in the LRC format.

### `currentTime` (required)

A number representing the current time of the audio being played. The `currentTime` prop should be updated on every `timeupdate` event of the audio player.

### `audioStatus` (required)

A boolean representing the audio played or paused. The `audioStatus` prop should be only true or false.

### `style` (nullable)

A object style representing the lyric Main BackgroundColor, Main TextColor, Main HighlightColor, Main FontSize,  Main FontWeight and Main FontFamily. The `style` prop should be only object or nullable.
- mainBackColor: The background color of the main content area.
- mainTextColor: The text color of the main content area.
- mainHighlightColor: The highlight color of selected text in the main content area.
- mainFontSize: The font size of the text in the main content area.
- mainFontWeight: The font weight (i.e., thickness) of the text in the main content area.
- mainFontFamily: The font family of the text in the main content area.

## Contributing

Contributions are welcome! If you find a bug or have a feature request, please open an issue on the [GitHub Pages](https://github.com/SiThu34297/sabahna-audio-lyric-doc-issue/issues).

## License

`sabahna-audio-lyric` is licensed under the MIT License. See the [LICENSE](https://github.com/SiThu34297/sabahna-audio-lyric-doc-issue/blob/master/LICENSE) file for more information.
