---
tags:
  - AI
title: Renaming books with AI
date: 2026-03-17T09:34:24.484Z
lastmod: 2026-03-17T10:28:28.744Z
---
## Warning! AI!

I know, I know... AI... However I think this is an use case were I actually think AI was the best tool to handle this task.

(I also thought it would be funny to have my first actual post in here to be about AI in this day and age we live in)

## The problem

Over the years I have accumulated a few e-books and PDFs from various online courses and the occasional [Humble Bundle](https://www.humblebundle.com/) drop.

The problem I have is that most of them came with file names that are quite hard for a person to read or search.

While some of them have underscores in place of spaces like `kubernetesanddocker_anenterpriseguide.pdf` and would be easy to rename with an one-liner, others like `continuousdeliverywithdockerandjenkins.pdf` omit the space between the words entirely and would require manual renaming and I'm too lazy for that (hence why they stayed like that for years).

## Action

I chose to use [Google's Gemini](https://gemini.google.com) because its one of the AI agents that I have the most familiarity with and because there is nothing in here that I would deem confidential or sensitive.

The prompt:

```
I have multiple digital copies of books and magazines in my computer, however most of them have file names are hard for a person to read. Attached is the output from "find" command with a list of all the books, generate a better file name for each book and give back a command to rename all of the books. Assume command to rename the books will be run from the same directory as the 'find' command.
```

Truncated file path input:

```
./DevOps
./DevOps/.DS_Store
./DevOps/PDF
./DevOps/PDF/kubernetesinproductionbestpractices.pdf
./DevOps/PDF/kubectl_command-linekubernetesinanutshell.pdf
./DevOps/PDF/hands-onkubernetesonwindows.pdf
./DevOps/PDF/hands-onkubernetesonazure.pdf
./DevOps/PDF/dockerfordevelopers.pdf
./DevOps/PDF/kubernetesanddocker_anenterpriseguide.pdf
./DevOps/PDF/kubernetes_acompletedevopscookbook.pdf
./DevOps/PDF/devopscultureandpracticewithopenshift.pdf
./DevOps/PDF/hands-ondockerformicroserviceswithpython.pdf
./DevOps/PDF/dockercertifiedassociatedca_examguide.pdf
./DevOps/PDF/hands-onmicroserviceswithkubernetes.pdf
./Linux books/classicshellscripting.mobi
./Linux books/linuxsystemprogramming.epub
./Linux books/learningtheviandvimeditors_7thedition.mobi
./Linux books/linuxpocketguide_3rdedition.pdf
./Linux books/introducingregularexpressions.epub
./Linux books/masteringregularexpressions.pdf
./1626920479134-DevSecOps_Essentials_StudyGuide_1547144130.pdf
./Qiao Liang Wang Xiangsui - Unrestricted Warfare-PLA Literature and Arts Publishing House 1999.pdf
./Coding
./Coding/algorithmsinanutshell.pdf
./Coding/headfirstagile_ebook.pdf
./Coding/becomingabetterprogrammer.pdf
./Coding/apprenticeshippatterns.pdf
./Coding/introductiontomachinelearningwithpython.epub
./Coding/learningcoredns.epub
./Coding/97thingseveryprogrammershouldknow.epub
./Coding/regularexpressionscookbook.epub
./Coding/artofreadablecode.epub

...
```

Truncated AI output command:

```sh
# --- Root Level & SRE ---
mv "./1626920479134-DevSecOps_Essentials_StudyGuide_1547144130.pdf" "./DevSecOps Essentials Study Guide.pdf"
mv "./1611073912946-DevSecOps Essentials PDF (1).pdf" "./DevSecOps Essentials.pdf"
mv "./Qiao Liang Wang Xiangsui - Unrestricted Warfare-PLA Literature and Arts Publishing House 1999.pdf" "./Unrestricted Warfare (1999).pdf"

# --- DevOps PDF ---
mv "./DevOps/PDF/kubernetesinproductionbestpractices.pdf" "./DevOps/PDF/Kubernetes in Production Best Practices.pdf"
mv "./DevOps/PDF/kubectl_command-linekubernetesinanutshell.pdf" "./DevOps/PDF/Kubectl Command-Line - Kubernetes in a Nutshell.pdf"
mv "./DevOps/PDF/hands-onkubernetesonwindows.pdf" "./DevOps/PDF/Hands-On Kubernetes on Windows.pdf"
mv "./DevOps/PDF/hands-onkubernetesonazure.pdf" "./DevOps/PDF/Hands-On Kubernetes on Azure.pdf"
mv "./DevOps/PDF/dockerfordevelopers.pdf" "./DevOps/PDF/Docker for Developers.pdf"
mv "./DevOps/PDF/kubernetesanddocker_anenterpriseguide.pdf" "./DevOps/PDF/Kubernetes and Docker - An Enterprise Guide.pdf"
mv "./DevOps/PDF/kubernetes_acompletedevopscookbook.pdf" "./DevOps/PDF/Kubernetes - A Complete DevOps Cookbook.pdf"
mv "./DevOps/PDF/devopscultureandpracticewithopenshift.pdf" "./DevOps/PDF/DevOps Culture and Practice with OpenShift.pdf"
mv "./DevOps/PDF/hands-ondockerformicroserviceswithpython.pdf" "./DevOps/PDF/Hands-On Docker for Microservices with Python.pdf"
mv "./DevOps/PDF/dockercertifiedassociatedca_examguide.pdf" "./DevOps/PDF/Docker Certified Associate (DCA) Exam Guide.pdf"
mv "./DevOps/PDF/hands-onmicroserviceswithkubernetes.pdf" "./DevOps/PDF/Hands-On Microservices with Kubernetes.pdf"

...
```

## Conclusion

While some of the renames weren't 100% what I would have liked, for the less than 5min it took me to get a list of files, and write a prompt to Gemini I think it was well worth it.

I think its important to reiterate that I would have not used an online AI model for this task if it involved documents with sensible information on them, even if I'm only passing the name of the document to it, a local model would have probably been a better choice.
