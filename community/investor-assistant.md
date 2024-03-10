# Building an Investor Type Quiz App

This comprehensive guide will take you through the steps of creating an investor type quiz app using ReByte's tools, in conjunction with the Typeform API. Typeform's API allows for the creation of user-friendly forms and surveys, making it an ideal choice for engaging with users in a clear and effective manner.

This is the final result of the app:

![app](https://res.cloudinary.com/dfjwtidnh/image/upload/v1710077600/investor-0_uqamir.png)

## Prerequisites

* A [Typeform account](https://www.typeform.com/), along with a thorough understanding of the [Typeform API documentation](https://www.typeform.com/developers/).
* Basic familiarity with ReByte's agent and app, as well as some programming knowledge.

## How to Build

The app operates on a straightforward logic. It begins by collecting basic information from the user, then generates a form using the Typeform API to ask more detailed questions. After the user completes and submits the form, their responses are analyzed to determine their investor type.

### Steps

1. **Gather information from the user's input:** 

   Utilize ReByte's `model-chat` action to extract information based on the user's initial input.

   ![gather info](https://res.cloudinary.com/dfjwtidnh/image/upload/v1710077600/intestor-1_vj3kej.png)

2. **Create a form using the Typeform API:**
   
   Implement pre-written code to select appropriate questions for the form. A call to the Typeform API via the "" action then generates a form URL.

![code](https://res.cloudinary.com/dfjwtidnh/image/upload/v1710077600/investor-2_sun44v.png)

3. **Collect the user's response:**

   Once the user submits the completed form, retrieve the results through the "http" action.

![get results](https://res.cloudinary.com/dfjwtidnh/image/upload/v1710077600/investor-3_k9ejp9.png)

4. **Analyze the user's input:**

   Use a subsequent model chat action to process the user's responses and identify their investor type.

   ![analyze](https://res.cloudinary.com/dfjwtidnh/image/upload/v1710077600/investor-4_puom38.png)

### Conclusion

This project demonstrates the power of integrating APIs like Typeform with ReByte's technology to create interactive, user-focused applications. The investor type quiz app not only engages users in a dynamic way but also provides valuable insights into their investment preferences, assisting them in making informed decisions. The steps outlined in this guide offer a framework that can be adapted to various applications, showcasing the flexibility and potential of these tools in the field of app development.

## Demos

To see the app and agents in action, explore the following links:

[Investor Type Quiz Agent](https://rebyte.ai/p/21b2295005587a5375d8/callable/ffdc7bd0d262b62cbd03/editor)

[Investor Type Quiz App](https://rebyte.ai/copilot/0167ad764f8be5e1bd41/session/6afc350466)
