
#Git issues and development workflow

0. Creation of a task
1. Brainstorming the task
2. Begin the task
3. During the development
4. Task completion
5. Code and functional review
6. Task release
7. Client QA on target website


#0. Creation of a task

Provide all the necessary info to complete the task.

- Set Pipeline: Backlogs
- Set an assignee (from assignee list) 
- Set a priority label: high, medium or low.
- Assign task to a milestone.
- Provide estimate (needs the ZenHub extension)

#1. Brainstorming the task

If there are questions, the assignee must ask the questions and notify the person who can answer with @mention.

- Set label: question

Once the questions are answered, then move to step 2.

- Remove label: question

#2. Begin the task

If all the info is given, the assignee can start the task.

- Set Pipeline: In Progress

#3. During the development

If the person has a question or needs help during the development, then he should just use the @mention to ask the question within the issue.
The @mention will notify the appropriate person.

If more info is required, then the developer will answer.

- Set label: help wanted
- Assign to: the person he thinks can provide an answer

#4. Task completion

***IMPORTANT REQUIREMENTS:***
1. All the committed code must work. 
2. It must not break existing code which could lead unit tests failing. 
3. If a task requires several commits to be completed, let the lead dev know in order to do a partial release of the task.
4. Also, to speed up the step 5 (code review), always try to do small commits as it is easier to validate. Of course, if updates or code additions are related, then it should be committed under the same commit.

Once the above requirements are met, the developer lets the reviewer know about it using the @mention.
The developer needs to provide details to perform unit testing. Just the unit test(s) to verify is sufficient.

- Set Pipeline: Code Review
- Assign to: The reviewer

#5. Code and functional review

The reviewer will verify if the front-end does what the specification states. If it does, he sets the task to release. Otherwise, he asks the developer to modify his work to meet the specifications.

For release:
- set Pipeline: Release
- assign to: the responsable of deployment

For reworking/updating: 
- set Pipeline: In Progress
- assign to: original developer.
- comment: explain what is not done properly.

#6. Task release

After a few tasks are reviewed or if a given task that is urgent and must be released, the responsable of deployment will prepare a release.

- Set version:MAJOR.minor.patch.build (build is found on Travis at the last commit of the last task completed for the release)
- Set a tag: MAJOR.minor.patch.build

Once the release is live, the responsable of deployment let the client know by email.

- Set Pipeline: Review/QA
- Assign to: none

#7. Client QA on target website

The client will perform a QA to test the integrity of the application and will test that each task completed gives the expected output.

If the task is completed successfully:
- the reviewer closes the issue

Otherwise, we go back to step 4 above:
- set status:in dev
- assign to: original developer
- provide details about the task rejection

