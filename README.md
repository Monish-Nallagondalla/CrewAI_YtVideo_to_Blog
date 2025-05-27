# CrewAI YouTube Video to Blog

This project leverages the CrewAI framework to create a blog post from YouTube video content. It uses AI agents to research video transcriptions on a specified topic from a YouTube channel and generate a summarized blog post. The application focuses on topics like AI, Machine Learning, Deep Learning, and Data Science, using the `@krishnaik06` YouTube channel as the primary source.

## Project Overview

- **Purpose**: Automate blog content creation by extracting and summarizing information from YouTube videos.
- **Framework**: CrewAI, utilizing AI agents for research and writing tasks.
- **Key Features**:
  - Research agent fetches video transcriptions for a given topic.
  - Writing agent creates a blog post based on the research.
  - Output is saved as a markdown file (`new-blog-post.md`).
- **GitHub Repository**: [CrewAI_YtVideo_to_Blog](https://github.com/Monish-Nallagondalla/CrewAI_YtVideo_to_Blog.git)

## Topics
- AI content generation
- YouTube video transcription
- CrewAI framework
- Blog automation
- Data Science and Machine Learning

## Tech Stack
- **Language**: Python
- **Framework**: CrewAI
- **Libraries**: crewai, crewai_tools, python-dotenv
- **APIs**: OpenAI (GPT-4), YouTube Channel Search Tool
- **Tools**: GitHub

## File Structure
```
CrewAI_YtVideo_to_Blog/
├── .gitignore          # Ignored files for Git
├── LICENSE            # Project license
├── README.md          # Project documentation
├── agents.py          # Defines AI agents for research and writing
├── crew.py            # Configures CrewAI and task execution
├── requirements.txt   # Python dependencies
├── tasks.py           # Defines research and writing tasks
├── tools.py           # Configures YouTube search tool
```

## Prerequisites
- Python 3.8+
- OpenAI API key (set in `.env` file)
- GitHub repository cloned: [CrewAI_YtVideo_to_Blog](https://github.com/Monish-Nallagondalla/CrewAI_YtVideo_to_Blog.git)
- YouTube channel handle (`@krishnaik06`) for video content

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Monish-Nallagondalla/CrewAI_YtVideo_to_Blog.git
   cd CrewAI_YtVideo_to_Blog
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**:
   - Create a `.env` file in the project root.
   - Add your OpenAI API key:
     ```env
     OPENAI_API_KEY=your_openai_api_key
     ```

## Usage

1. **Configure Agents and Tasks**:
   - `agents.py`: Defines a research agent to fetch YouTube video transcriptions and a writing agent to create blog content.
   - `tasks.py`: Specifies tasks for researching video content and writing a summarized blog post.
   - `tools.py`: Configures the YouTube search tool for the `@krishnaik06` channel.
   - `crew.py`: Sets up the CrewAI framework with sequential task execution.

2. **Run the Application**:
   ```bash
   python crew.py
   ```
   - The script processes the topic `AI VS ML VS DL vs Data Science` by default.
   - Output is saved as `new-blog-post.md` in the project directory.

3. **Customize Topic**:
   - Modify the topic in `crew.py` by updating the `inputs` dictionary:
     ```python
     result = crew.kickoff(inputs={'topic': 'Your_New_Topic'})
     ```

## Code Details

- **agents.py**:
  - `blog_researcher`: Fetches video transcriptions for the specified topic using the YouTube search tool.
  - `blog_writer`: Generates a blog post summarizing the video content.
- **tasks.py**:
  - `research_task`: Produces a 3-paragraph report based on video content.
  - `write_task`: Creates a summarized blog post saved as `new-blog-post.md`.
- **tools.py**:
  - Configures `YoutubeChannelSearchTool` for the `@krishnaik06` channel.
- **crew.py**:
  - Orchestrates agents and tasks using CrewAI's sequential process.
  - Configures memory, caching, and a maximum RPM of 100.

## Output
- The generated blog post is saved as `new-blog-post.md` in the project directory.
- The research task produces a 3-paragraph report, and the writing task summarizes it into a blog post.

## Dependencies
Listed in `requirements.txt`:
- `crewai`
- `crewai_tools`
- `python-dotenv`

## Notes
- Ensure a valid OpenAI API key is set in the `.env` file.
- The YouTube search tool requires internet access to fetch video transcriptions.
- The application is configured for the `@krishnaik06` YouTube channel; modify `tools.py` to use a different channel.
- The OpenAI model used is `gpt-4-0125-preview`; update `agents.py` if a different model is preferred.

## Contributing
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit changes (`git commit -m "Add feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions or issues, open a GitHub issue or contact the repository owner at [Monish-Nallagondalla](https://github.com/Monish-Nallagondalla).
