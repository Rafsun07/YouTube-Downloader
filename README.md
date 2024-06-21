# YouTube-Downloader

YouTube Downloader is a simple Python script that allows users to download YouTube videos in the highest resolution available. It uses the pytube library to fetch video details and perform the download.

## Features

- Download videos: Downloads YouTube videos in the highest resolution available.
- Fetch video details: Displays the title and view count of the video before downloading.

## Installation

1. **Clone the repository:**

    ```
    git clone https://github.com/Rafsun07/YouTube-Downloader.git
    cd YouTube-Downloader
    ```

2. **Run the program:**

    ```
    python youtube-downloader.py
    ```

## Usage

1. **Start the program:**

    Run the `youtube-downloader.py` script to start the Mad Libs game.

    ```
    python youtube-downloader.py
    ```

2. **Input Prompts:**

    The program will prompt you to enter an adjective, two verbs, and a famous person's name. For example:

    ```
    Enter the YouTube URL: <paste-your-youtube-url-here>
    
    ```

3. **Output:**

    The program will generate and display a Mad Libs story using your inputs. For example:

    ```
    Title: <video-title>
    Views: <video-views>
    Download complete.
    
    ```

## How the Code Works

1. **Importing the `pytube` Library::**

    ```
    from pytube import YouTube
    ```
    
    - This line imports the `YouTube` class from the `pytube` library, which is necessary for interacting with YouTube videos.

2. **Handling Errors:**

    ```
    try:
    ```
    - The `try` block is used to handle any exceptions that might occur during the execution of the code.
    
3. **Getting User Input:**

    ```
    url = input("Enter the YouTube URL: ")
    ```

    - This line prompts the user to input a YouTube URL. The URL entered by the user is stored in the variable `url`.
    
4. **Creating a YouTube Object:**

    ```
    yt = YouTube(url)
    ```
    
    - This line creates a `YouTube` object using the URL provided by the user. This object, `yt`, contains various attributes and methods to interact with the video.
    
5. **Displaying Video Details:**

    ```
    print("Title:", yt.title)
    print("Views:", yt.views)
    ```

    - These lines print the title and the number of views of the YouTube video. `yt.title` and `yt.views` are attributes of the `YouTube` object that provide information about the video.

6. **Getting the Highest Resolution Stream:**

    ```
    yd = yt.streams.get_highest_resolution()
    ```

    - This line fetches the stream with the highest resolution available for the video. `yt.streams` returns a list of all available streams, and `get_highest_resolution()` selects the one with the highest resolution.

7. **Downloading the Video:**

    ```
    yd.download()
    ```

    - This line downloads the selected stream (the highest resolution) to the current directory. The `download()` method is called on the stream object `yd`.

8. **Confirming Download Completion:**

    ```
    print("Download complete.")
    ```
    
    - This line prints a message indicating that the download is complete. 

9. **Handling Exceptions:**

    ```
    except Exception as e:
        print("An error occurred:", str(e))
    ```

    - The `except` block catches any exceptions that occur during the execution of the `try` block. If an error occurs, it prints a message along with the error details.

### Summary:

- Input: The user is prompted to enter a YouTube video URL.
- Process:
    - A `YouTube` object is created using the provided URL.
    - The title and view count of the video are displayed.
    - The highest resolution stream is selected.
    - The selected stream is downloaded to the current directory.
- Output: Confirmation of download completion or an error message if something goes wrong.

This script provides a simple and effective way to download YouTube videos using the `pytube` library, making it easy for users to retrieve videos by simply providing a URL.

## Additional Sections:

### FAQ

Q: What if the download fails?

A: Make sure you have a stable internet connection and the provided URL is correct. If the issue persists, check if the video is available on YouTube.

Q: Can I download videos in a specific resolution?

A: This script is designed to download the highest resolution available. However, you can modify the script to select a specific resolution using `pytube`.

### Troubleshooting

Issue: `pytube.exceptions.RegexMatchError: get_throttling_function_name: could not find match for multiple`

Solution: Update `pytube` to the latest version as YouTube often changes their website structure, and `pytube` releases updates to handle these changes.


## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the project's coding standards and includes appropriate tests.

## Contact

For questions, suggestions, or issues, please open an issue on GitHub or contact the project maintainer at [rafsun.eram@gmail.com](mailto:rafsun.eram@gmail.com).

## Acknowledgements

- Developed using Python.

---
