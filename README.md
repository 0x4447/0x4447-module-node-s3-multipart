# S3 Multipart Module

A module that allwos you to take advantage of multipart upload over S3 which gives you 5TB of file size transfer over the Borwser or NodeJS with a simple to use API. 

# Frame of reference

This module allows you to upload a single or mutliple file at the same time. If you select mutliple files, they will be added to a queue, and uplaoded one after the other. The API works based on the Event system. This means that you have to subscribe to the events listed bellow to get back all the details of what is going on with your file(s).

# Documentation

This simple API should allow you to build any type of UI.

### Initialization

n/a

## Events

### Selection
```javascript
s3mm.on('selection', function(selection) {

    console.log(selection.file.list);

});
```

### Info
```javascript
s3mm.on('info', function(info) {

    console.log(info.file.name);
    console.log(info.data.size);
    console.log(info.chunk.size);
    console.log(info.time.started);

});
```

### Progress

```javascript
s3mm.on('progress', function(progress) {

    console.log(progress.info.file.name);
    console.log(progress.data.uploaded);
    console.log(progress.chunk.peace);
    console.log(progress.upload.speed);

});
```

### Done
```javascript
s3mm.on('done', function(done) {

    console.log(done.file.name);
    console.log(done.time.elapsed);

});
```


