
#Git issues and development workflow

0. Creation of a task
1. Brainstorming the task
2. Begin the task
3. During the development
4. Task completion
5. Code and functional review
6. Task release
7. Client QA on target website

#Requirements

Please add ZenHub extension to your GitHub account. The extension can be found here: [https://www.zenhub.io/](https://www.zenhub.io/)


#0. Creation of a task

Provide all the necessary info to complete the task.

- Set Pipeline: Backlogs
- Set an assignee (from assignee list) 
- Set a priority label: high, medium or low.
- Assign task to a milestone.
- Provide estimate

#1. Brainstorming the task

If there are questions, the assignee must ask the questions and notify the person(s) who can answer with @mention.

- Set label: question
- Assign to: the person he thinks can provide an answer

Once the questions are answered, then move to step 2.

- Remove label: question

#2. Begin the task

If all the info is given, the assignee can start the task.

- Set Pipeline: In Progress

#3. During the development

If the person has a question or needs help during the development, then he should just use the @mention to ask the question within the issue.
The @mention will notify the appropriate person or persons.

- Set label: help wanted
- Assign to: the person he thinks can provide an answer

#4. Task completion

***IMPORTANT REQUIREMENTS:***
1. All the committed code must work. 
2. It must not break existing code which could lead unit tests failing. 
3. If a task requires several commits to be completed, let the lead dev know in order to do a partial release of the task.
4. Also, to speed up the step 5 (code review), always try to do small commits as it is easier to validate. Of course, if updates or code additions are related, then it should be committed under the same commit.
5. In relation the previous point, always make sure your code was developped backward compatible with the previous functional state and that, in the case of a large task being split into several smaller tasks, each small accomplish the goal set with breaking the integrity of the application.

Once the above requirements are met, the developer lets the reviewer know about it using the @mention.
The developer needs to provide details to perform unit testing or just provide the build number and the list of the unit test(s) to verify is sufficient. See https://travis-ci.org/Puzzlout/{TargetRepository}

- Set Pipeline: Code Review
- Assign to: The reviewer

#5. Code and functional review

The reviewer will verify if the front-end does meet the specifications. If it does, he sets the task to release. Otherwise, he asks the developer to modify his work to meet the specifications.

For release:
- set Pipeline: Release
- assign to: the responsable of deployment

For reworking/updating: 
- set Pipeline: In Progress
- assign to: original developer.
- comment: explain what is not done properly.

#6. Task release

After a few tasks are reviewed or if a given task that is urgent and must be released, the responsable of deployment will prepare a release.

- Set version:MAJOR.minor.patch.build (last build is found on Travis at the last commit of the last task completed for the release)
- Set a tag: MAJOR.minor.patch.build

Once the release is live, the responsable of deployment lets the client know by email.

- Set Pipeline: Review/QA
- Assign to: none

#7. Client QA on target website

The client will perform a QA to test the integrity of the application and will test that each task completed gives the expected output.

If the task is completed successfully:
- the reviewer closes the issue

Otherwise, we go back to step 3 above:
- Set Pipeline: In Progress 
- Assign to: original developer
- Provide details about the task rejection

