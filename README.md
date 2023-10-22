# Bleatography Photo Archive Theme

A minor adapdation of the thumbsup theme in the forked repo

## How to use

### Dependencies

Install [thumbsup](https://thumbsup.github.io/) and its dependencies.

Run `npm install moment` in working directory. Time parsing depends on this.

### Input Structure

Structure the input folder in a way that folders containing photos are albums. An album is allowed to contain subalbums. Example:

```txt
input
├── album1
│   ├── group1
│   │   ├── pic1.jpg
│   │   └── pic2.jpg
│   └── group2
│       ├── pic3.jpg
│       ├── pic4.jpg
│       └── pic5.jpg
├── album2
│   ├── pic6.jpeg
│   ├── pic7.jpg
│   └── pic8.jpg
├── standalone1.jpg
└── standalone2.jpg
```

Use the `IPTC - Content > Description` metadata to add caption for photos

### Configuration

Create a `config.json` file somewhere with the following information:

```json
{
    "input": ".../input", // path to photo input folder
    "output": ".../output", // where to generate output

    // See https://thumbsup.github.io/docs/3-configuration/cheat-sheet/ 
    // for what these do
    "small-size": "300", 
    "large-size": "1200",
    "cleanup": "false",
    "album-page-size": "0",
    "albums-output-folder": "albums",

    // If you want to watermark your photos
    "watermark": ".../watermark.png", // path to watermark png
    "watermark-position": "SouthEast", // location

    "theme-path": ".../archive", // path to the root of this repo

    "title": "PhotoArchive", // Website title
    "footer": "these are placeholder images from unsplash", // website footer

    "dummy": "dummy" // this does nothing (*ﾟ▽ﾟ*)
}
```

### Build

Then run the following to generate static website

```bash
thumbsup --config "path/to/config.json"
```

### Customise theme

Motify any `.hbs` or `.less` file. 

See [thumbup documentation](https://thumbsup.github.io/docs/4-themes/create/).

### Deployment

Any platform for deploying static website should work. Some ideas:
- Netlify
- GitHub Pages
- Wunderbucket 

## Licence

Template files (i.e. those not in `public`) under MIT.

Libraries:

- Thumbsup is under MIT
- lightGallery is under GNU GPL license v3
- Justified Gallery is under MIT
