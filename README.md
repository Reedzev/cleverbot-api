# CleverbotAPI
Simple library, interacting with cleverbot's api. **You can find information about the usage of the library in [it's wiki](https://github.com/Jqmey/cleverbot-api/wiki).**

## Example
```javascript
const CleverbotAPI = require('cleverbot-api');
const cleverbot = new CleverbotAPI('API-KEY');

console.log('Just a small town girl');
cleverbot.getReply({ input: 'Just a small town girl' }, (error, response) => {
    if(error) throw error;
    console.log(response.output);
    cleverbot.getReply({ input: response.output, cs: response.cs }, (error, response) => {
        if(error) throw error;
        console.log(response.output);
        cleverbot.getReply({ input: response.output, cs: response.cs }, (error, response) => {
            if(error) throw error;
            console.log(response.output);
        });
    });
});
```