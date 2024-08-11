# K-Groove

K-Groove is an app that leverages Google Gemini AI to analyze users' dance movements and transform them into K-pop style choreography. Users can practice their own K-pop dances while receiving real-time feedback. This app provides K-pop fans with an easy and enjoyable dance learning experience, contributing to greater accessibility to dance.

## Project Overview

As K-pop gains worldwide popularity, many people aspire to dance like K-pop idols. However, mastering professional dance moves can be challenging. K-Groove was created to address this challenge.

## Key Features

- **Motion Analysis**: Gemini AI analyzes users' dance moves or short videos uploaded to the app.
- **K-pop Style Transformation**: Transforms users' movements into K-pop idol-style dance moves.
- **Real-time Feedback**: Provides instant feedback on areas that need improvement.

## Technology Stack

- Google Gemini AI
- Jupyter Notebook

## Target Users
 
- K-pop fans
- Dance beginners
- Individuals looking to improve their dance skills

## Team

K-Groove was developed by team 'MANDU', currently studying at Microsoft AI School in South Korea.

- **Erika**: Planner
- **Whoru**: Developer

## Getting Started

To get started with K-Groove, follow these steps:

1. Install Visual Studio Code (VSCode) on your computer.
2. Install the Jupyter Notebook extension for VSCode.
3. Locate the 'expert-dance.mp4' file, which contains a portion of NewJeans' "How Sweet" dance.
4. Practice the choreography shown in the video, focusing on the approximately 19-second segment.
5. Record your own dance performance, mimicking the choreography from the expert video.
6. Save your dance video as 'user_dance.mp4' and place it in the same directory as the project files.
7. Set up the [GEMINI_API_KEY](https://aistudio.google.com/app/apikey) environment variable (see instructions below).
8. Open and run the 'Untitled-1.ipynb' file in VSCode.

### Setting up the GEMINI_API_KEY environment variable

Before running the application, you need to set up the GEMINI_API_KEY environment variable. Follow the instructions for your operating system:

#### Windows:

1. Open the Start menu and search for "Environment Variables".
2. Click on "Edit the system environment variables".
3. In the System Properties window, click on the "Environment Variables" button.
4. Under "User variables", click "New".
5. Set the Variable name as GEMINI_API_KEY and the Variable value as your actual Gemini API key.
6. Click "OK" to save.

Alternatively, you can use the command prompt:

#### macOS and Linux:

1. Open your terminal.
2. Open your shell configuration file (e.g., ~/.bash_profile, ~/.zshrc, or ~/.bashrc) in a text editor.
3. Add the following line at the end of the file: `export GEMINI_API_KEY=<your-api-key-here>`
4. Save the file and exit the editor.
5. Run the following command to apply the changes:

### Creating Pose Images and Videos

If you want to generate pose images and videos:

1. Run the 'Untitled-2.ipynb' file in VSCode.
2. This will create image files in the `expert` and `user` folders.
3. It will also generate pose videos: 'expert_pose.mp4' and 'user_pose.mp4'.

Note: Errors may occur during image file generation. If an error occurs after creating expert image files, follow these steps:
- Restart the kernel
- Run from the beginning, but skip this part:
  ```python
  with create_pose_landmarker() as landmarker:
      print("Processing expert video...")
      user_poses = process_video(expert_video, landmarker, show_first_n_frames=720, path="expert")

## Milestone
 
- Short-term: Build a diverse K-pop choreography database, improve the user interface
- Mid-term: Add community features for users, offer tutorials at various difficulty levels
- Long-term: Develop an immersive learning environment using AR/VR technology, expand into global markets

## K-Groove’s unique features set it apart from other similar apps in several ways
 
Google Gemini AI Integration: K-Groove utilizes advanced Google Gemini AI to analyze users' dance movements with precision and transform them into K-pop style choreography. This cutting-edge technology ensures accurate movement recognition and style conversion, which is not commonly found in other dance apps.
 
Real-time Feedback: Unlike many apps that simply offer pre-recorded tutorials, K-Groove provides real-time feedback by comparing the user's movements to standard K-pop dance moves. This feature allows users to immediately correct and improve their dance skills.
 
K-pop Specific Focus: While other dance apps may cover a broad range of styles, K-Groove is tailored specifically to K-pop fans. It offers a K-pop-centric learning environment, making it the go-to app for those passionate about this genre.
 
Personalized Learning: K-Groove offers a personalized learning experience by analyzing user data and tailoring the training program to the individual's level and preferences. This focus on customization helps users progress at their own pace.
 
## K-Groove has several strategic plans for future development 
Short-term: The app will focus on expanding its K-pop choreography database and improving the user interface to make the learning experience more intuitive and engaging.
 
Mid-term: K-Groove plans to introduce community features that allow users to interact and share experiences with each other, fostering a sense of belonging. Additionally, the app will offer tutorials at various difficulty levels to cater to a wider range of users, from beginners to more advanced dancers.
 
Long-term: K-Groove aims to leverage AR/VR technologies to create an immersive learning environment, where users can practice in a virtual setting that feels like a real K-pop dance studio. Moreover, the app has ambitions to expand into global markets, making K-pop dance accessible to fans worldwide.
 
## Issues and Solutions Encountered During Project Implementation
Problem with Using Gemini Vision Features
 
Problem Situation:
Attempted to implement a feature that analyzes videos of experts and users using the Gemini API and provides feedback.
Encountered a persistent "OTHER" error during the video upload and API request process.
 
Attempted Solutions:
Uploaded individual videos and made separate API requests.
Uploaded both videos simultaneously and then made an API request.
 
Results:
The same "OTHER" error occurred in all attempts, leading to the abandonment of this method.
Alternative Approach Using MediaPipe
 
New Approach:
Analyzed pose data from experts and users using MediaPipe.
Requested feedback and improvements from the Gemini API based on the analyzed data.
 
Problem Encountered:
Experienced a timeout issue when transmitting data longer than 5 seconds.
 
Solution:
Gradually reduced the size of the data array.
Adjusted the amount of data to an optimal level that the Gemini API could respond to.
 
Results:
Successfully resolved the timeout issue and implemented the desired functionality.
 
Conclusion:
Although the initial plan to use Gemini's vision features was abandoned due to persistent errors, the project's core functionality was successfully implemented using an alternative approach with MediaPipe. The timeout issue encountered during data processing was resolved by adjusting the data size, allowing the project to achieve its goals.
 
 
## Video Script
 ```txt
[Erika]:
Hello, we are the team 'MANDU'. I'm Erika, the planner, and this is Whoru, the developer. Today, we are excited to introduce our project, called 'K-Groove'.  We are now studying at Microsoft AI School in South Korea.
 
K-pop has become a global phenomenon, and many people aspire to dance like K-pop idols. However, mastering professional dance moves is not easy. That's why we developed this app to help users practice their own K-pop style.
 
[Whoru]:
'K-Groove' allows users to upload their own motions or short dance videos, which are then analyzed by Google's AI model, Gemini. After analyzing the user's movements, Gemini transforms them into K-pop style dance moves and suggests areas for improvement if needed.
Let's now demonstrate how the app works.
 
[Erika]:
Here, you can see a dance video uploaded by User. The app analyzes this video and transforms it into a K-pop idol style. As you can see, users receive real-time feedback, allowing them to practice and perfect their dance moves.
 
[Whoru]:
This technology utilizes Google's Gemini AI to provide accurate and fast analysis. It offers an easy and fun way for anyone to learn K-pop dances. We believe this app will be a valuable tool for K-pop fans.
 
[Erika]:
In conclusion, 'K-Groove' is a platform that allows users to express their creativity. It helps users not only imitate but also refine their own unique styles while dancing like K-pop idols.
Thank you for listening to our presentation. With 'K-Groove', you can make your K-pop idol dreams come true!
```
---

Make your K-pop idol dreams come true with K-Groove!
