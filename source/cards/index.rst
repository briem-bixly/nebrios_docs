============
Card Scripts
============

Nebri allows users to spawn UI's quickly with very little code. These UI's are currently in the form of "cards". A card is a `Polymer <https://www.polymer-project.org/1.0/docs/>`_ element. We chose this route because of Polymers growing momentum, their vast library of elements, and Material Design.

There are two main routes you can take when creating Polymer elements in Nebri. The quick option is to use the NebriElement behavior and extend it with your own form fields and html. Very little code is needed to create powerful Material Design forms for your users. Many things are done automatically for you when you take this route, such as closing after it has been submitted, validation, and more.

Nebri Cards
***********

Example card code:

.. code-block:: html

    <dom-module id="hello-world">
        <template>
            <h2>Hello World</h2>
            <p>This is an example NebriOS Card.</p>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-string id="testy"></nebri-string>
            </nebri-form>
        </template>
        <script>            
            Polymer({
                is: "hello-world",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

Results in this card:

.. image:: /img/hello_world.png

.. note:: All card names must use **hyphens** not underscores.

The target defines which route the form fields will be saved by. In this case they hit a default api module which you can see in the API doc. More to come later about Template Cards. The following works inside the ``<template>`` tag. 


.. code-block:: html

    <nebri-string id="string"></nebri-string>
    <nebri-integer id="integer"></nebri-integer>
    <nebri-float id="float"></nebri-float>
    <nebri-boolean id="boolean"></nebri-boolean>
    <nebri-textarea id="textarea"></nebri-textarea>
    <nebri-email id="email"></nebri-email>
    <nebri-phone id="phone"></nebri-phone>
    <nebri-zipcode id="zipcode"></nebri-zipcode>
    <nebri-time id="time"></nebri-time>
    <nebri-date id="date"></nebri-date>
    <nebri-datetime id="datetime"></nebri-datetime>
    <nebri-checklist id="checklist"></nebri-checklist>
    <nebri-multi-select id="multi_select"></nebri-multi-select>
    <nebri-string-list id="string_list"></nebri-string-list>
    <nebri-dictionary id="dictionary"></nebri-dictionary>

Optional arguments include
==========================

    * label 
        * for instruction purposes
    * required  
        * is the field required?
    * disabled
        * is the field disabled?
    * defaultValue 
        * setting the starting value; if this is not specified, the input defaults to an appropriate empty value
    * value 
        * for data binding

.. note :: `required` and `disabled` do not need an argument and can be passed as an empty attribute

Example: ``<nebri-integer id="integer" label="Integer" required></nebri-integer>``

Available Attributes
====================

With the upgrade to Polymer 1.0, we've leveraged attributes to make validation a little easier. Here's a full list of attributes that are
available along with which inputs accept them:

* type: the type that the input should be cast as; i.e. password
    * nebri-string
* placeholder: a placeholder for the input; note: if a label is not specified, the placeholder will behave like a label
    * nebri-string
    * nebri-textarea
    * nebri-email
    * nebri-phone
    * nebri-zipcode
    * nebri-time
    * nebri-date
    * nebri-datetime
* pattern: a pattern to validate the input with
    * nebri-string
    * nebri-float
    * nebri-phone
    * nebri-zipcode
* char-counter: if this attribute is present, a character counter will be display beneath the input
    * nebri-string
    * nebri-textarea
* max-length: the maximum length of the input
    * nebri-string
    * nebri-textarea
* min-length: the minimum length of the input
    * nebri-string
    * nebri-textarea
* step: specifies a numeric increment
    * nebri-integer
    * nebri-float
* max: the maximum value of the input
    * nebri-integer
    * nebri-float
    * nebri-time
    * nebri-date
    * nebri-datetime
* min: the minimum value of the input
    * nebri-integer
    * nebri-float
    * nebri-time
    * nebri-date
    * nebri-datetime
* regex: a regex expression to validate the input with
    * nebri-email
* country-code: country-code can be supplied if the input should support phone numbers from outside the U.S. Defaults to +1.
    * nebri-phone
* phone-number-pattern: The format of a valid phone number, including formatting but excluding the country code. Use 'X' to denote the digits separated by dashes. Defaults to 'XXX-XXX-XXXX'.
    * nebri-phone
* options: an array of options for the input
    * nebri-checklist - options objects should include label, value and checked properties; if checked is not provided, default is false
    * nebri-multi-select - options objects should include label, value and selected properties; if selected is not provided, default is false
* max-select: the maximum items that can be selected
    * nebri-checklist
    * nebri-multi-select
* min-select: the minimum items that can be selected
    * nebri-checklist
    * nebri-multi-select
* entries: a list of items of a type that matches the input
    * nebri-string-list - entries should all be of type string or should be castable to a string
* max-entries: the maximum number of items allowed
    * nebri-string-list
* min-entries: the minimum number of items allowed
    * nebri-string-list
* fields: a list of field objects for a nebri-dictionary; fields should have a property `type` to specify what kind of input is needed

For input examples: :doc:`inputs`

Validation
==========

Looking to validate inputed values before they hit your system? For example, making sure a string is filled in if a checkbox is checked:

.. code-block:: html

    <dom-module id="validation-test">
        <template>
            <nebri-form id="form" target="default.save_form">
                <nebri-string id="string" label="String" on-string-validate="validate"></nebri-string>
                <nebri-boolean id="boolean" label="boolean" on-boolean-validate="validate"></nebri-boolean>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "validation-test",
                behaviors: [NebriElement],
                validate: function(e, detail, sender) {
                    if (this.$.boolean.value && this.$.string.value == "") {
                        this.$.string.setError('This is required!');
                    } else {
                        this.$.string.removeError();
                    }
                }
            });
        </script>
    </dom-module>

If your validation requires a specific value, we've made it easy to add error messages!

.. code-block:: html

    <dom-module id="validation-test">
        <template>
            <nebri-form id="form" target="default.save_form">
                <nebri-string id="string" label="String" on-string-validate="validate"></nebri-string>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "validation-test",
                behaviors: [NebriElement],
                validate: function(e, detail, sender) {
                    if (detail.newValue != 'lol') {
                        detail.sender.setError('Value must be lol.');
                    } else {
                        detail.sender.removeError();
                    }
                }
            });
        </script>
    </dom-module>


Deep validation is also possible in dictionaries!

.. code-block:: html

    <dom-module id="validation-test">
        <template>
            <nebri-form id="form" target="default.save_form">
                <nebri-dictionary id="dictionary1" fields="[[fields1]]" on-dictionary-validate="validate"></nebri-dictionary>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "validation-test",
                behaviors: [NebriElement],
                properties: {
                    fields1: {
                        type: Array,
                        value: [
                            {'type': 'string', 'id': 'string', 'label': 'A String', 'value': 'bar'},
                            {'type': 'integer', 'id': 'integer', 'label': 'An Integer', 'placeholder': '6'},
                            {'type': 'boolean', 'id': 'boolean', 'label': 'A Checkbox', 'value': true}
                        ]
                    }
                },
                validate: function(e, detail, sender) {
                    if (detail.newValue.string != 'foo') {
                        detail.sender.setError('String should be foo');
                    } else {
                        detail.sender.removeError();
                    }
                }
            });
        </script>
    </dom-module>

Manual Cards
************

The manual method allows you do anything you like within a card without being bound to the nebri-element defaults. These are just Polymer elements, so any HTML/CSS/JS that would normally work within a Polymer element is fair game.

.. code-block:: html

    <link rel="import" href="/static/paper-slider/paper-slider.html">
    <link rel="import" href="/static/paper-item/paper-item.html">
    <dom-module id="paper-demo">
        <template>
            <h2>Material Design FTW!</h2>
            <paper-slider></paper-slider>
            <core-selector>
                <paper-item>Item 1</paper-item>
                <paper-item active>Item 2</paper-item>
                <paper-item>Item 3</paper-item>
            </core-selector>
        </template>
        <script>
            Polymer({
                is: "paper-demo",
                behaviors: [NebriElement],
            });
        </script>
    </dom-module>


And would render the following card:


.. image:: /img/material_design_form.png


Accessing Cards
***************

Cards are seen in the default home page of your NebriOS admin. They show up automatically there for a number of reasons. Any user that is on your account experiences the same thing, except they see only the cards meant for them. Lastly, cards can be show on your Nebri url (something.nebrios.com) to public users also should you have any publicly accessible cards.


How do you actually get a card to show? Inside of any Rule Script you can call :doc:`../builtins/load_card`. By doing this you send a card to whichever user activated the script which activated load_card().

A simple method we use while testing is the qa_card_loader.py rule script loading cards for you. Copy this script to your instance:

.. code-block:: html


    class qa_card_loader(NebriOS):
        listens_to = ['qa_card_name', 'pid', 'user']

        def check(self):
            return self.qa_card_name

        def action(self):
            self.qa_card_loader_status = "Ran at: %s" % datetime.now()

            if self.pid:
                self.card_pid = self.pid
            else:
                self.card_pid = self.PROCESS_ID

            if self.user:
                self.card_user = self.user
            else:
                self.card_user = self.last_actor

            load_card(self.qa_card_name, pid=self.card_pid, user=self.card_user)


And enter this in debug mode to load your card:

::

    qa_card_name := example-card

You will see example-card appear in your home screen, supposing that card exists.
