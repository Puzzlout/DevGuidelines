
#Git issues and development workflow

1. Creation of a task / issue
2. Begin task/issue
3. During the development
4. Task completion
5. Function review
6. Task(s) code review
7. Task release
8. Review of release on dev.fieldworkmanager.com


#1. Creation of a task / issue

Provide all the necessary info to complete the task.

- Set a status, assignee (lead dev, freelancer) and priority label.
- Assign task/issue to a milestone.
- Assign to: developer

***Remark:*** assignee label is used to know what kind of person works on a task. As far as our project goes, freelancer is the main assignee. The lead dev is FWAJL.
So the assignee label is for you to know what I'm working on and what freelancers are doing.

#2. Begin task/issue

If all the info is given, the person, that is assigned to the task, can start.

- Set status:in dev

#3. During the development

If the person has a question during the development, then he should just use the @mention to ask the question within the issue.
The @mention will notify the appropriate person.

If more info is required, then the developer will answer.

- Set status:more info required
- Assign to: the person he thinks can provide an answer

#4. Task completion

***IMPORTANT REQUIREMENT:*** all the committed code must work. It must not break existing code which could lead unit tests failing. 
If a task requires several commits to be completed, let the lead dev know in order to do a partial release of the task.
Also, to speed up the step 6 (code review), always try to do small commits as it is easier to validate. Of course, if updates or code additions are related, then it should be committed under the same commit.

Once the above requirement is met, the developer has committed all the work. He lets the front-end reviewer lead dev about it using the @mention​, set the proper label(s) and assign the task to the reviewer.
The developer needs to provide details to perform unit testing. Just some sentences describing how to test is sufficient.

- Set status:function review​
- Assign to: front end reviewer

#5. Function review

The front-end reviewer will verify if the front-end does what SOW states. If it does, he requests the lead to review the code.

For validation:
- set status:code review
- assign to: lead dev

For reworking/updating: 
- set status:in dev
- assign to: original developer

#6. Task(s) code review​

The lead dev review the tasks done and validate them if they are ok or ask the developer to make updates as described.

For validation:
- set status:to release
- assign to: lead dev

For reworking/updating: 
- set status:in dev
- assign to: original developer
#7. Task release

After a few tasks are reviewed or if a given task that is urgent and must be released, the lead dev will prepare a release.

- Set status:to release
- Set version:MAJOR.minor.patch.build

Once the release is live, the lead dev let the reviewer know using the @mention.

- Set status:unit testing
- Assign to: reviewer

#8. Review of release on test or production website URL

The reviewer will perform a unit test to test the integrity of the application and will test each task.
If the task is completed successfully:
- set status:live
- the reviewer closes the issue

Otherwise, we go back to step 5 above:
- set status:in dev
- assign to: original developer

