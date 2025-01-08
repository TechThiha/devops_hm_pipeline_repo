# DevOps Homework

Welcome to the **HenOps DevOps Homework**! This repository contains workflows, artifacts, and results that demonstrate key DevOps principles. Most files in this project branch are png files, so **Git Large File Storage (LFS)** is used to manage them efficiently. Follow the guide below to get started.

---

## Table of Contents
[Answers to Task D](#answers-to-task-d)
1. [How did you test your pipelines?](#how-did-you-test-your-pipelines)
   - [Pipeline Script from SCM Setup](#pipeline-script-from-scm-setup)
   - [Pipelines](#pipelines)
   - [Why Extra Pipeline](#why-extra-pipeline)
2. [How did you test repoC Python?](#how-did-you-test-repoc-python)
3. [Advantages of Using Git LFS](#advantages-of-using-git-lfs)
4. [How to Adjust This Repository to Support Git LFS](#how-to-adjust-this-repository-to-support-git-lfs)
5. [Alternatives to Git LFS](#alternatives-to-git-lfs)
6. [Key Workflows and Results](#key-workflows-and-results)
   - [Pipeline B](#pipeline-b)
   - [Pipeline C](#pipeline-c)
   - [Extra Pipeline](#extra-pipeline)

---

## Answers to Task D

### How did you test your pipelines?

Each pipeline was tested with separate projects.
**Manual Trigger to run pipeline**: 
   - Configured pipelines in the repository to run all the workflow.
   - Monitored the logs for successful execution of all pipeline stages.

**Jenkins Plugin Usage**: 
   - HTML Publisher plugin (Version-1.37) is used to test the results faster.
     - By using this we can avoid downloading the artifact and extracting the archive.
     - we can also avoid multiple clicks to reach the file.

**Private Repo Access**: 
   - Define github account in Jenkins Global Credentials to let the pipeline access to the private repo.

**Trigger Pipeline from SCM**: 
   - Can also use the Global Credentials to use pipeline from scm without writing the codes in the jenkins UI.
   - Here's how the pipeline is set up as shown below.

### Pipeline Script from SCM Setup
- **Define Source Code path**:  
  ![Pipeline Setup from SCM](pipeline_setup_cred.png)
- **Define File**:  
  ![Pipeline B Artifact](pipeline_setup_script.png)

### Pipelines
- [Pipeline B](#pipeline-b)
- [Pipeline C](#pipeline-c)
- [Extra Pipeline](#extra-pipeline)

### Why Extra Pipeline
- **To save time**: By optimizing tasks, we can reduce the processing time needed for each operation.
- **Improved Efficiency**: Automating certain processes allows the system to work faster.
- **Cost-effective**: By reducing the time and resources used, the extra pipeline helps save costs.

---

### How did you test repoC Python?

To test the Python scripts in `repoC`, the following steps were followed:
- **Obtain Jenkins Log**: Download and review the log file from Jenkins pipeline as artifact.
- **Write Python Code**: Based on the log, write Python code to process the task.
- **Set Up Virtual Environment**: Create a virtual environment to isolate dependencies.
- **Use Default Plugins**: Use only the default plugins for data transformation.
- **Run the Script**: Execute the Python script in the virtual environment.
- **Verify Output**: Check the output for accuracy and ensure it meets requirements.
- **Upload Results**: Once satisfied, upload the results to `repoC`.

This method ensures proper testing of the Python code while maintaining a clean environment.

---

### Advantages of Using Git LFS
The repository `repoA-doc` contains binary files, and using **Git LFS (Large File Storage)** for these files has some important benefits:

- **Faster Performance**: It keeps the repository small by replacing big files with tiny pointers, which makes cloning and fetching faster.
- **Better Storage**: Large files are stored separately, so the repository doesn’t get too big.
- **Easier Collaboration**: Contributors only download the versions of large files they need, saving time and space.
- **Better File Handling**: Git LFS works well for files like `.png` or `.zip` that don’t work well with Git’s regular compression.

Learn more about Git LFS: [https://git-lfs.github.com/](https://git-lfs.github.com/)

---

### How to Adjust This Repository to Support Git LFS

To configure this repository for Git LFS, follow these steps:

1. **Install Git LFS**:
   ```bash
   git lfs install
   ```
2. **Track Large File Types**:
   Identify the file types to track and add them to Git LFS:
   ```bash
   git lfs track "*.png"
   ```
3. **Push Files**:
   Add and push files as usual. Git LFS will handle large files:
   ```bash
   git add .
   git commit -m "Add Large file"
   git push -u origin taskD
   ```

For more detailed instructions, refer to:  
- [Git LFS Documentation](https://git-lfs.github.com/)  
- [GitHub’s Guide to Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files)  

---

### Alternatives to Git LFS

While Git LFS is the recommended solution, here are some alternatives:
1. **Cloud Storage Links**:
   - Store large files in cloud services (e.g., AWS S3, Google Drive) and include download links in the repository.
   - Pros: No repository size limitations.
   - Cons: Requires external dependency management.

2. **Submodules**:
   - Use Git submodules to reference another repository containing the large files.
   - Pros: Keeps the main repository smaller.
   - Cons: Additional complexity in managing submodules.

3. **Artifact Repositories**:
   - Use artifact repositories like Nexus or Artifactory to store binaries.
   - Pros: Centralized binary storage for CI/CD.
   - Cons: Requires setup and maintenance.

---

## Key Workflows and Results

Below are the pipelines and associated files used in this project:

### Pipeline B
- **Workflow**:  
  ![Pipeline B](pipelineB.png)
- **Artifact**:  
  ![Pipeline B Artifact](pipelineB_artifact.png)
- **Results**:  
  ![Pipeline B Result](pipelineB_results.png)

### Pipeline C
- **Workflow**:  
  ![Pipeline C](pipelineC.png)
- **Artifact**:  
  ![Pipeline C Artifact](pipelineC_artifacts.png)
- **Results**:  
  ![Pipeline C Result](pipelineC_results.png)

### Extra Pipeline
- **Workflow**:  
  ![Extra Pipeline](extra_pipeline.png)
- **Artifact**:  
  ![Extra Pipeline Artifact](extra_pipeline_artifacts.png)
- **Results**:  
  ![Extra Pipeline Result](extra_pipeline_results.png)

---

This guide answers Task D and ensures that large files are managed efficiently, and the repository structure is also defined as mentioned in the Tasks. Happy coding! 🚀
