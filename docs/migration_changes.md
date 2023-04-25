# Migration Changes

Following the Olive migration process, it was time to migrate the Scorm xblock. Because the history of this xblock is confusing, the approach taken to migrate was to test it in the new version, see if it worked and if not, make the necessary changes to make it work.

## Changes applied

Changed celery 'task' decorator for 'shared_task' for the s3_upload task. This change has to do with celery itself, that implemented shared_task as the way to create isolated tasks for a Django app. Also one of the calls of the task was changed from s3_upload() to s3_upload.delay() since it was not executing correctly in a worker with redis.

## Refactoring

The additional changes made to the xblock was some refactoring of the code to adapt it to new Python code standards.