# BasicLambdaFunction--FulfillmentLex
Basic lambda function for the fulfillment section of AWS Lex (bot)

exports.handler = (event, context, callback) => {
    // when intent get fulfilled, inform lex to complete the state
    var topic = event.currentIntent.slots.Topics;
    let response = {sessionAttributes: event.sessionAttributes,
      dialogAction: {
        type: "Close",
        fulfillmentState: "Fulfilled",
        message: {
          contentType: "PlainText",
          content: "Thanks for the desire to collaborate with " + topic + " topic." + " " + "Let's keeping touch, here my email: albertohernandez2288@gmail.com"
        }
      }
    }
    callback(null, response);
};

##Note:
In this example the variable topic is referring to the name of the slot Topics, which is one that i used for my the test. You can change this with the "name slots" use in your bot.
