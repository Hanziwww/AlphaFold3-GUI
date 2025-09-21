<p>
</p>
<p>
</p>
<p>
</p>
<p>
</p>
<p>
</p>
<p>
</p>

<h1 align="center"> AFusion: AlphaFold3 GUI(Graphical User Interface)</h1>

<p align="center">
    <img src="https://img.shields.io/badge/Python-3.10-blue.svg">
    <img src="https://img.shields.io/badge/Framework-Streamlit-green.svg">
    <img src="https://img.shields.io/badge/Model-AlphaFold3-orange.svg">
    <a href="https://pypi.org/project/afusion/">
        <img src="https://img.shields.io/badge/PyPI-afusion-purple.svg">
    </a>
    <a href='https://alphafold3-gui.readthedocs.io/en/latest/?badge=latest'>
        <img src='https://readthedocs.org/projects/alphafold3-gui/badge/?version=latest' alt='Documentation Status'>
    </a>
</p>

![image](https://github.com/user-attachments/assets/d1d894c7-c0cc-4218-9677-1917c1ad7b88)

<p align="center">
    Transform your protein structure prediction workflow with AFusion - a sleek, intuitive graphical interface that makes AlphaFold3 accessible to everyone. No more command-line hassles - just point, click, and predict.
</p>

<p align="center">
     Developed by Han Wang and Chunjie Tian @Tianlab
</p>

**[Demo site](https://af3gui.streamlit.app/)** *(generate input JSON files ONLY)*

[**Usable visualization site**](https://af3vis.streamlit.app/) *(fully usable)*

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation and Running](#installation-and-running)
- [Usage](#usage)
  - [Launching AFusion](#launching-afusion)
  - [Using the GUI](#using-the-gui)
  - [Enhanced Visualization Features](#enhanced-visualization-features)
- [Documentation](#documentation)
- [ToDo](#todo)
- [Screenshots](#screenshots)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## ✨ Key Features

### Installation & Setup
- **GUI Installer**: Step-by-step visual installation wizard
- **Auto-Configuration**: Handles environment setup and dependencies

### Core Functionality
- **Visual Workflow**: Clean, modern interface for job configuration 
- **Multi-Entity Support**: Process proteins, RNA, DNA, and ligands
- **Advanced Options**: Customize MSA, templates, and modifications

### Execution & Control
- **🚀 Integrated Pipeline**: Direct AlphaFold3 execution from GUI
- **🖥️ Live Monitoring**: Real-time process tracking and console output
- **🧩 Batch Processing**: Python API for automated predictions

### **🌟 New Features!**
- **AlphaFold 3 Output Analysis System**: Automatically analyze and visualize results with customizable visualizations and generate detailed PDF reports for streamlined insights.
- **Enhanced Visualization Features** (New in this fork):
  - Multiple visualization styles (cartoon, stick, line, sphere)
  - Flexible coloring schemes (confidence, chain, secondary structure, rainbow)
  - Interactive residue selection and chain sequence viewer
  - Advanced export capabilities for scientific and 3D printing formats
  - Improved PAE matrix visualization and confidence metrics display

## Prerequisites

Before using AFusion, ensure that you have the following:

1. **🐳 Docker Installed**: Docker is required to run AlphaFold 3. Install Docker from the [official website](https://www.docker.com/get-started/).

2. **🧬 AlphaFold 3 Installed**: AFusion requires AlphaFold 3 to be installed and set up on your system. Follow the installation instructions provided in the [AlphaFold 3 GitHub Repository](https://github.com/google-deepmind/alphafold3) to deploy AlphaFold 3. **Or you can run step-by-step GUI by**:

   ```bash
   afusion install
   ``` 

3. **🐍 Python 3.10 or Higher**: AFusion is built with Python and requires Python 3.10 or higher.

## Installation and Running

1. **Install AFusion**

   Run the following command in your terminal to install AFusion:

   ```bash
   pip install afusion
   ```

2. **Run AFusion GUI**

   After installation, you can start AFusion by running:

   ```bash
   afusion run
   ```

   This will launch the AFusion graphical user interface (GUI) in your default web browser.

**Please Note:**

- **🧬 AlphaFold 3 Installation**: Ensure you have correctly installed AlphaFold 3, including model parameters and required databases, following the [AlphaFold 3 Installation Guide](https://github.com/google-deepmind/alphafold3/blob/main/docs/installation.md).

- **⚙️ Docker Configuration**: After installing Docker, make sure it is running properly and that your user has permission to execute Docker commands.

- **📦 Streamlit is Included in Dependencies**: AFusion's installation will automatically install all required dependencies, including Streamlit. There's no need to install it separately.

## Usage

### Launching AFusion

1. **🚀 Start the Streamlit App**

   From the project directory, run:

   ```bash
   afusion run
   ```

2. **🌐 Access the Application**

   - The application will launch, and Streamlit will provide a local URL (e.g., `http://localhost:8501`).
   - Open the provided URL in your web browser to access AFusion.

### Using the GUI

**Find more about input in [here](https://github.com/google-deepmind/alphafold3/blob/main/docs/input.md)**.

#### 1. Welcome Page

- **👋 Logo and Introduction**: You'll see the AFusion logo and a brief description.
- **📑 Navigation Sidebar**: Use the sidebar on the left to navigate to different sections of the app.

#### 2. Job Settings

- **🏷️ Job Name**: Enter a descriptive name for your job.
- **🔢 Model Seeds**: Provide integer seeds separated by commas (e.g., `1,2,3`).

#### 3. Sequences

- **🔬 Number of Entities**: Select how many entities you want to add (Proteins, RNA, DNA, Ligand).
- **📋 Entity Details**: For each entity:
  - **⚛️ Entity Type**: Select the type (Protein, RNA, DNA, Ligand).
  - **🆔 Entity ID**: Provide an identifier for the entity.
  - **🧬 Sequence Input**: Enter the sequence information.
  - **✏️ Modifications**: Optionally add modifications with their types and positions.
  - **📂 MSA Options**: Choose MSA generation options and provide MSA data if applicable.
  - **📜 Templates**: Optionally add template data with mmCIF content and indices.

#### 4. Bonded Atom Pairs (Optional)

- **🔗 Add Bonds**: Check the box to add bonded atom pairs.
- **⚛️ Define Bonds**: For each bond, provide details for the first and second atoms, including entity IDs, residue IDs, and atom names.

#### 5. User Provided CCD (Optional)

- **📜 User CCD Input**: Paste or enter custom CCD data in mmCIF format.

#### 6. Generated JSON

- **📄 Review JSON Content**: The application generates the JSON input file based on your entries. You can review it here.

#### 7. AlphaFold 3 Execution Settings

- **🗂️ Paths Configuration**:
  - **📁 AF Input Path**: Specify the path to the AlphaFold input directory (e.g., `/home/user/af_input`).
  - **📂 AF Output Path**: Specify the path to the output directory (e.g., `/home/user/af_output`).
  - **📂 Model Parameters Directory**: Provide the path to the model parameters directory.
  - **📂 Databases Directory**: Provide the path to the databases directory.

- **⚙️ Execution Options**:
  - **🏗️ Run Data Pipeline**: Choose whether to run the data pipeline (CPU-intensive).
  - **💻 Run Inference**: Choose whether to run inference (requires GPU).

#### 8. Run AlphaFold 3

- **💾 Save JSON File**: Click the "Save JSON File" button to save the generated JSON to the specified input path.
- **▶️ Run AlphaFold 3 Now**: Click the "Run AlphaFold 3 Now ▶️" button to execute the AlphaFold 3 prediction using the Docker command.
  - **🔧 Docker Command**: The exact Docker command used is displayed for your reference.
  - **📊 Command Output**: Execution output is displayed within the app for monitoring.


## Documentation
- Full Documentation in [here](https://alphafold3-gui.readthedocs.io)

## ToDo

- [X] ~~📄 **Bulid Documentation:** Tutorial for using the AFusion API in Python scripts for batch predictions.~~
- [X] ~~♻️ **Refactor Code and Publish to PyPI**: Refactor the project code for improved modularity and maintainability, and publish the latest version to PyPI for easy installation.~~
- [X] ~~🔗 **Develop AlphaFold result analysis system**: Design and implement a comprehensive analysis pipeline for AlphaFold prediction results.~~
    - [X] ~~Update the system.~~
- [ ] ⚛️ **Preset Common Small Molecules & Metal Ions**: Add a dedicated section for quick access to commonly used small molecules and metal ions.  
- [ ] 🛠️ **New Tool for Chemical Small Molecules**: Develop a new tool to handle and model chemical small molecules, supporting seamless integration into the prediction pipeline.  
- [X] ~~🖥️ **Add Console Output**: Implement a backend console for output to track processes and debug more effectively.~~
- [X] ~~🧩 **Create API for Batch Predictions**: Develop a standalone function API to allow users to perform batch predictions with afusion in Python scripts.~~
- [X] ~~**🧭 Create Guided Installation GUI**: To simplify the installation process.~~
- [X] ~~**🎨 Enhanced Visualization Features**: Implement advanced visualization capabilities with multiple styles and export options.~~

## Screenshots

### Visualization GUI Interface

<details>
  <summary>Click to view screenshot</summary>
  
  <img width="1165" alt="image" src="https://github.com/user-attachments/assets/1480db8e-5a11-43ad-8c46-b54dbe333f66" />

</details>

### Installation GUI Interface
<details>
  <summary>Click to view screenshot</summary>
  
  ![image](https://github.com/user-attachments/assets/f083aad7-c3b0-4d1d-b670-7de91804c9b0)
</details>

### CLI Output
<details>
  <summary>Click to view screenshot</summary>
  
  ![image](https://github.com/user-attachments/assets/66bb3789-c2d5-4be2-894b-a779136e8d83)
</details>


## License

This project is licensed under the GPL3 License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- **Original Project**: Created by [Hanziwww](https://github.com/Hanziwww)
- **Visualization Enhancements**: This fork includes additional visualization features while maintaining the core functionality of the original project
- **Enhanced Version**: Maintained by [Shivp1413](https://github.com/Shivp1413)
- **AlphaFold 3**: This GUI is designed to work with [AlphaFold 3](https://github.com/google-deepmind/alphafold3) by DeepMind
- **Streamlit**: AFusion is built using [Streamlit](https://streamlit.io/)
- **Contributors**: Thanks to all contributors to the original project!

---

If you encounter any issues or have suggestions for improvements, please open an [issue](https://github.com/Hanziwww/AlphaFold3-GUI/issues) or submit a [pull request](https://github.com/Hanziwww/AlphaFold3-GUI/pulls).

Happy Folding! 🧬
