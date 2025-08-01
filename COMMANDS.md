# CV Template Commands Guide

This guide explains all the custom commands available in this LaTeX CV template.

## Quick Start

1. Copy the template folder: `cp -r template/ your-name/`
2. Edit `your-name/personal-data.tex` with your information
3. Modify `your-name/cv.tex` using the commands below
4. Compile from your folder: `cd your-name/ && pdflatex main.tex`

## Basic Structure Commands

### Contact Header
```latex
\contactheader
```
Creates the header with your name, contact information, and social links using variables from `personal-data.tex`.

### About Me Section
```latex
\aboutme{Your description here...}
```
Creates an "About me" section with automatic date footer.

## Section Environments

### Education Section
```latex
\begin{education}
    \educationentry{Degree Title}{Start Date -- End Date}{Institution}{City, Country}{Description}
    \educationentry{Another Degree}{Date Range}{Institution}{Location}{Description}
\end{education}
```

**Example:**
```latex
\begin{education}
    \educationentry{BS. in Computer Science - GPA: 3.8/4.0}{2020 -- 2024}{MIT}{Cambridge, MA}{
        Relevant courses: Machine Learning, Data Structures, Algorithms.
        Thesis: "Deep Learning Applications in Computer Vision"
    }
\end{education}
```

### Professional Experience Section
```latex
\begin{experiences}
    \experience{Job Title}{Start Date -- End Date}{Company Name}{Description}
    \experience{Another Job}{Date Range}{Company}{Description}
\end{experiences}
```

**Example:**
```latex
\begin{experiences}
    \experience{Software Engineer}{Jan 2024 -- Present}{Google}{
        Developed machine learning models for search ranking algorithms.
        Improved query response time by 15% through optimization techniques.
    }
\end{experiences}
```

### Academic Experience Section
```latex
\begin{academicexperiences}
    \academicexperience{Position}{Date Range}{Institution}{Description}
\end{academicexperiences}
```

### Awards Section
```latex
\begin{awards}
    \award{Award Name}{Organization, Year}
    \award{Another Award}{Organization, Year}
\end{awards}
```

## Activities Section

The activities section contains multiple subsections:

```latex
\begin{activities}
    % Presentations
    \begin{presentations}
        \presentation{Year}{Title}{Description}
    \end{presentations}
    
    % Conferences/Congresses
    \begin{congresses}
        \congress{Year}{Conference Name}
    \end{congresses}
    
    % Research Projects
    \begin{researchprojects}
        \researchproject{Date Range}{Project Title}{Supervisor info}{Description}
    \end{researchprojects}
    
    % Courses/Materials
    \begin{courses}
        \course{Year}{Course Title}{Description}
    \end{courses}
    
    % Selected Projects
    \begin{selectedprojects}
        \selectedproject{Year}{Project Title}{Description}
    \end{selectedprojects}
    
    % Work in Progress
    \begin{workinprogress}
        \workprogress{Date Range}{Project Title}{Collaborators}
    \end{workinprogress}
\end{activities}
```

### Individual Activity Commands

#### Presentations
```latex
\presentation{2024}{Machine Learning in Healthcare}{
    Presented at the International Conference on AI in Medicine.
    Discussed novel approaches to medical image analysis.
}
```

#### Conferences
```latex
\congress{2024}{International Conference on Machine Learning (ICML)}
```

#### Research Projects
```latex
\researchproject{2023 -- 2024}{Deep Learning for Medical Imaging}{Supervised by Prof. Jane Smith}{
    Developed convolutional neural networks for automated diagnosis.
    Published results in Nature Machine Intelligence.
}
```

#### Courses/Materials
```latex
\course{2024}{Introduction to Python Programming}{
    Created comprehensive course materials including videos and exercises.
    Course taken by over 500 students with 95% satisfaction rate.
}
```

#### Selected Projects
```latex
\selectedproject{2023}{COVID-19 Data Visualization Platform}{
    Interactive web dashboard built with React and D3.js.
    Visualized pandemic trends across 50+ countries.
    Available at: https://covid-viz.example.com
}
```

#### Work in Progress
```latex
\workprogress{2024 -- Present}{Quantum Machine Learning Algorithms}{joint work with Dr. Alice Johnson (MIT) and Dr. Bob Wilson (Stanford)}
```

## References Section

```latex
\referencessection

\reference{Prof. John Doe, PhD}{john.doe@university.edu}{Research and Academic}
\reference{Jane Smith, CTO}{jane.smith@company.com}{Professional}
```

## Special Commands

### Technologies/Skills List
```latex
\technologies{Python, JavaScript, React, Machine Learning, TensorFlow, PostgreSQL, Docker, Kubernetes}
```

Creates a multi-column list of your technical skills.

## Advanced Customization

### Using Variables
All personal information is stored in `config/personal-data.tex`. You can use these variables anywhere:

- `\fullName` - Your full name
- `\email` - Email address
- `\currentPosition` - Current job/status
- `\currentInstitution` - Current institution
- `\researchFocus` - Main research area
- And many more...

**Example:**
```latex
\aboutme{
    I am currently a \currentPosition\ at \currentInstitution.
    My research focuses on \researchFocus.
}
```

### Section Titles
Customize section titles in `personal-data.tex`:
```latex
\newcommand{\educationTitle}{Educational Background}
\newcommand{\experienceTitle}{Work Experience}
% etc.
```

## Complete Example

Here's a minimal complete CV:

```latex
\contactheader

\aboutme{
    I am a passionate software engineer with 3 years of experience in machine learning.
    Currently working as a \currentPosition\ at \currentInstitution.
}

\begin{education}
    \educationentry{BS. Computer Science - GPA: 3.8/4.0}{2020 -- 2024}{MIT}{Cambridge, MA}{
        Focus on machine learning and artificial intelligence.
    }
\end{education}

\begin{experiences}
    \experience{Software Engineer}{2024 -- Present}{Google}{
        Developing ML models for search algorithms.
    }
\end{experiences}

\begin{awards}
    \award{Dean's List}{MIT, 2023}
    \award{Best Student Project}{IEEE Conference, 2024}
\end{awards}

\referencessection
\reference{Prof. Jane Smith}{jane.smith@mit.edu}{Academic}
```

## Tips

1. **Keep descriptions concise** - Use bullet points in descriptions for readability
2. **Use consistent date formats** - Stick to "Month Year -- Month Year" or "Year -- Year"
3. **Include quantifiable achievements** - Numbers and percentages make impact clear
4. **Update personal-data.tex first** - All your contact info is centralized there
5. **Test compilation frequently** - Run `pdflatex` often to catch errors early

## Troubleshooting

- **Command not found**: Make sure `\input{cv-commands}` is in your cv folder
- **Compilation errors**: Check for missing closing braces `}` in command arguments
- **Formatting issues**: Ensure you're using the correct number of arguments for each command
- **Missing personal data**: Copy `personal-data-template.tex` to `personal-data.tex`