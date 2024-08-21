# Youtube-dlp 📹

This is a library for web scraping YouTube. With this library you can get direct links to download video audio from YouTube

## Installation

`npm install youtube-dlp`

## Usage

```
import YoutubeDlp from "youtube-dlp";

/* Youtube-dl input options */
const youtubeDlOptions = {
    checkWorkingLinks: true,
    format: "all" /* audio, video, all */,
    torRequest: false
}

const youtubeDlp = new YoutubeDlp(youtubeDlOptions);

youtubeDlp.getVideoById("lJIQrI15_c8")
.then(res => console.log(res))
.catch(err => console.log(err))
```

To prevent YouTube from blocking you for frequent requests, it is recommended to enable TorRequest to make requests via the Tor network.

## Video

```
{
    video: {
        videoDetails: {
              videoId: string;
              title: string;
              lengthSeconds: string;
              keywords: string[];
              channelId: string;
              isOwnerViewing: boolean;
              shortDescription: string;
              isCrawlable: boolean;
              thumbnail: { thumbnails: {
                        url: string;
                        width: number;
                        height: number;
                }};
              allowRatings: boolean;
              viewCount: string;
              author: string;
              isPrivate: boolean;
              isUnpluggedCorpus: boolean;
              isLiveContent: boolean;
        };
        formats: /* Video formats */;
        adaptiveFormats: /* Video formats */;
    };
    responseOptions: {
    web: {
        userAgent: string;
        cookies: string;
    };
    android: {
        userAgent: string;
        cookies: string;
    };
    }
}

```

## Format

```
{
    itag: number;
    mimeType: string;
    bitrate: number;
    width: number;
    height: number;
    lastModified: string;
    quality: TQuality;
    initRange?: TRange;
    indexRange?: TRange;
    fps: number;
    qualityLabel: TQualityLabel;
    projectionType: string;
    audioQuality?: "AUDIO_QUALITY_MEDIUM" | "AUDIO_QUALITY_LOW";
    approxDurationMs: string;
    audioSampleRate: string;
    audioChannels: number;
    signatureCipher?: string;
    colorInfo?: TColorInfo;
    url: string;
    cipher?: string;
    ncode: string;
    sig: string;
}
```
