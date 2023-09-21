# Delivery Tracker 1

In this project, you will get some more practice by building a simple CRUD app from scratch.

Here is your target: 

[delivery-tracker-1.matchthetarget.com](https://delivery-tracker-1.matchthetarget.com/)

This project includes automated tests, so click on this button to get started:

LTI{Load Delivery Tracker 1 assignment}(https://grades.firstdraft.com/launch)[S9ymPy6WCsn18gLbByVbZQ7k]{vfdtzJb5bLYqYwuqgeRKpc5d}(10)[Delivery Tracker 1 Project]

Then, fork the repository and create your codespace.

Be sure to run `rake sample_data` at a bash prompt to hydrate your development database with some sample data. Remember, you can use `rails console` and the live app preview route `/rails/db` to explore your database tables whenever you need to. 

When you `bin/dev` you will be greeted by a completely blank app. Your mission is to match the target and get the `rake grade` specs to all pass.

## The target

[delivery-tracker-1.matchthetarget.com](https://delivery-tracker-1.matchthetarget.com/)

Try to Domain Model the target before you begin. To explore the target, sign up and create a few deliveries. You can also sign in with any of:

- `alice@example.com`
- `bob@example.com`
- `carol@example.com`
- `dave@example.com`
- `eve@example.com`

and password: `password`.

### Some behavior to note

- You can't do anything in the app until you sign up or sign in.
- The home page has a list of deliveries that you're expecting.
- There are two sections on the home page: "Waiting on" and "Received".
- You can log a new delivery using the form at the top of the page. Once added, it appears in the "Waiting on" section.
- You must provide a description and a date that the package is expected to arrive on, or the entry is not accepted.
- For items in the "Waiting on" section, there is a button that, when clicked, moves the item to the "Received" section.
- For items in the "Received" section, there is a link to delete the item.

### Implementation details that you must stick to

Among some other things, the `rake grade` specs will be looking for these:

- As usual, pay attention to the copy in buttons, links, labels, headings, etc — spelling, capitalization, and punctuation matter.
- The sign in page is located at `/users/sign_in`.
- The sign up page is located at `/users/sign_up`.
- The "Waiting on" section should be contained within a <div> that has the class `"waiting_on"`.
- The "Received" section should be contained within a <div> that has the class `"received"`.
- In the target, the field to enter a date is an <input type="date">. (This input type may not work properly on all browsers — use Chrome when testing.

### Optional implementation details

The following behavior in the target is optional, and `rake grade` will pass without them:

- The background-color of the "Waiting on" section is `lightgoldenrodyellow`.
- The background-color of the "Received" section should be `lightgreen`.
- For items in the "Waiting on" section, the date that the delivery was expected on is displayed. If the date is more than 3 days ago, the color of the date is red.

## Hints

Use `rails generate draft:resource` for models and `rails generate devise user` for user account models. Revisit the Bulletin Board lessons for the steps we took with those generators.

Recall the `current_user` variable made available throughout your app when you use Devise. See how we made use of that in the Bulletin Board 2 lesson. With devise, you can also add this line to your `ApplicationController` to force visitors to sign in before visiting any pages:

```ruby{4}
# app/controller/application_controller.rb

class ApplicationController < ActionController::Base
  before_action :authenticate_user!
  # ...
```

The specs _will not_ test for the color styling you see in the target; however, you could add some custom CSS rules to put in `public/css/my_styles.css` and connect them by adding this line to the `<head>` of your `application.html.erb`:

```erb
<!-- app/views/layouts/application.html.erb -->

<link rel="stylesheet" href="/css/my_styles.css">
```

Alternatively, you're welcome to get fancy and add a bit of Bootstrap to your version of the app! 

Whatever you do, the most important thing is that you get the `rake grade` specs to pass. Have fun!

---

- Approximately how long (in minutes) did this lesson take you to complete?
{: .free_text_number #time_taken title="Time taken" points="1" answer="any" }
	
---
