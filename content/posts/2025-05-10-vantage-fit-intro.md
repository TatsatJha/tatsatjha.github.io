+++
title = "Introducing Vantage-Fit"
date = "2025-05-10"
description = "An overview of the Vantage-Fit project thus far"
+++

Vantage-Fit is a project that has been in my head for about a year now. I had a major development cycle on it in the Summer of 2024 and I'm revisiting it now to properly finish the job. 

The idea behind Vantage-Fit was to create a training app that could provide as good of—or perhaps an even better training—advice compared to a personal-trainer at a fraction of the cost. For me this means making a program-builder, a progress-tracker, and an AI-toolkit that worked together to essentially emulate a personal-trainer.

### AI-toolkit

To me, this is the cornerstone of the app that brings it past a mere training app. And I feel I should address, while I do believe there's already too many training apps, I think there's a lot of training apps that are absolutely useless and if anything I feel better knowing there's another competent app like Vantage-fit out there taking up share in the market.

Anyhow, the AI-toolkit is itself planned to be composed of a few features but these features need to be using a competent model. As far as I'm concerned, in this area, most models are similar though at this point I believe I will be using Gemini because last I checked it was a very cheap model relatively, but I am also seriously considering using llama since it is open source.

Regardless, the plan is to make the model significantly more competent at personal training through a custom RAG pipeline and a certain degree of prompt engineering. The corpus of documents that Vantage-AI will be drawing on will be custom-written and ensure that Vantage AI has a clear understanding of my fundamental principles of training.

### Progress-tracker

The Progress tracker is at a glance going to be quite simple. I'm using Firebase as my backend, and so the actual progress tracking will be as simple as saving a completed session to firestore. The app will then display this tracked data on the home page and a few dashboards on other pages. The interesting part will be using this data to provide smart recommendations on which programs to run, which exercises to try, which areas of training you might want to shore up, and most imporantly, recommendations on progressive overload. 

### Program-builder

The program-builder is going to be the core of the actual experience. The idea really is to have users create their own programs and then share them with others. The actual program-builder is already mostly built but I'm unhappy with the ui and I need to update the way that data is stored and retrieved. The cool part here is that we'll be able to use AI to help provide auto-complete suggestions when making these training programs, so even beginner trainers who are not used to designing their own programs nor choosing the right program can still get started quickly.
