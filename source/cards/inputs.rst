==============
Input Examples
==============

String
******

.. code-block:: html

    <dom-module id="string-test">
        <template>
            <h2>String Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-string id="string1"></nebri-string>
                <nebri-string id="string2" label="Label For String"></nebri-string>
                <nebri-string id="string3" placeholder="Placeholder For String"></nebri-string>
                <nebri-string id="string4" label="Label" placeholder="Placeholder"></nebri-string>
                <nebri-string id="string5" disabled></nebri-string>
                <nebri-string id="string6" value="Preset Value" label="Label"></nebri-string>
                <nebri-string id="string7" label="Label For String" char-counter></nebri-string>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "string-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/string-example.png

Integer
*******

.. code-block:: html

    <dom-module id="integer-test">
        <template>
            <h2>Integer Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-integer id="integer1"></nebri-integer>
                <nebri-integer id="integer2" disabled></nebri-integer>
                <nebri-integer id="integer3" value="5"</nebri-integer>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "integer-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/integer-example.png

Float
*****

.. code-block:: html

    <dom-module id="float-test">
        <template>
            <h2>Float Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-float id="float1"></nebri-float>
                <nebri-float id="float2" disabled></nebri-float>
                <nebri-float id="float3" value="5.3"</nebri-float>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "float-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/float-example.png

Boolean
*******

.. code-block:: html

    <dom-module id="boolean-test">
        <template>
            <h2>Boolean Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-boolean id="boolean1" value="true" label="Already Checked"></nebri-boolean>
                <nebri-boolean id="boolean2" label="Required" required></nebri-boolean>
                <nebri-boolean id="boolean3" label="Disabled" disabled</nebri-boolean>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "boolean-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/boolean-example.png

Textarea
********

.. code-block:: html

    <dom-module id="textarea-test">
        <template>
            <h2>Textarea Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-textarea id="textarea1"></nebri-textarea>
                <nebri-textarea id="textarea2" label="Label For Textarea"></nebri-textarea>
                <nebri-textarea id="textarea3" placeholder="Placeholder For Textarea"></nebri-textarea>
                <nebri-textarea id="textarea4" disabled></nebri-textarea>
                <nebri-textarea id="textarea5" value="Preset Value" label="Label"></nebri-textarea>
                <nebri-textarea id="textarea6" label="Label For Textarea" char-counter></nebri-textarea>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "textarea-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/textarea-example.png

Email
*****

.. code-block:: html

    <dom-module id="email-test">
        <template>
            <h2>Email Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-email id="email1"></nebri-email>
                <nebri-email id="email2" label="Your Email"></nebri-email>
                <nebri-email id="email3" placeholder="em@ail.com"></nebri-email>
                <nebri-email id="email4" disabled></nebri-email>
                <nebri-email id="email5" value="my@email.com" label="Your Email"></nebri-email>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "email-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/email-example.png

Phone
*****

.. code-block:: html

    <dom-module id="phone-test">
        <template>
            <h2>Phone Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-phone id="phone1"></nebri-phone>
                <nebri-phone id="phone2" label="Your Phone Number"></nebri-phone>
                <nebri-phone id="phone3" placeholder="123-456-7890"></nebri-phone>
                <nebri-phone id="phone4" disabled></nebri-phone>
                <nebri-phone id="phone5" country-code="+33"></nebri-phone>
                <nebri-phone id="phone6" phone-number-pattern="XXXX-XXXX-XX" value="1234-5678-90"></nebri-phone>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "phone-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/phone-example.png

Zipcode
*******

.. code-block:: html

    <dom-module id="zipcode-test">
        <template>
            <h2>Zipcode Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-zipcode id="zipcode1"></nebri-zipcode>
                <nebri-zipcode id="zipcode2" label="Your Zipcode"></nebri-zipcode>
                <nebri-zipcode id="zipcode3" placeholder="12345"></nebri-zipcode>
                <nebri-zipcode id="zipcode4" disabled></nebri-zipcode>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "zipcode-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/zipcode-example.png

Time
****

.. code-block:: html

    <dom-module id="time-test">
        <template>
            <h2>Time Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-time id="time1"></nebri-time>
                <nebri-time id="time2" label="Your Time"></nebri-time>
                <nebri-time id="time3" placeholder="11:30"></nebri-time>
                <nebri-time id="time4" disabled></nebri-time>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "time-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/time-example.png

Date
****

.. code-block:: html

    <dom-module id="date-test">
        <template>
            <h2>Date Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-date id="date1"></nebri-date>
                <nebri-date id="date2" label="Your Date"></nebri-date>
                <nebri-date id="date3" placeholder="03/23/1989"></nebri-date>
                <nebri-date id="date4" disabled></nebri-date>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "date-test",
                behaviors: [NebriElement],
                });
        </script>
    </dom-module>

.. image:: /img/inputs/date-example.png

Checklist
*********

.. code-block:: html

    <dom-module id="checklist-test">
        <template>
            <h2>Checklist Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-checklist id="checklist1" options="[[options]]"></nebri-checklist>
                <nebri-checklist id="checklist2" options="[[options]]" disabled></nebri-checklist>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "checklist-test",
                behaviors: [NebriElement],
                properties: {
                    options: {
                        type: Array,
                        value: [
                            {'label': 'A', 'value': 'A'},
                            {'label': 'B', 'value': 'B', 'checked': true},
                            {'label': 'C', 'value': 'C'},
                        ]
                    }
                }
                });
        </script>
    </dom-module>

.. image:: /img/inputs/checklist-example.png

String List
***********

.. code-block:: html

    <dom-module id="string-list-test">
        <template>
            <h2>String List Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-string-list id="string_list1" value="[[options]]"></nebri-string-list>
                <nebri-string-list id="string_list2" disabled></nebri-string-list>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "string-list-test",
                behaviors: [NebriElement],
                properties: {
                    options: {
                        type: Array,
                        value: [
                            'foo',
                            'bar',
                            'baz'
                        ]
                    }
                }
                });
        </script>
    </dom-module>

.. image:: /img/inputs/stringlist-example.png

Dictionary
**********

.. code-block:: html

    <dom-module id="dictionary-test">
        <template>
            <h2>Dictionary Examples</h2>
            <nebri-form id="test_form" target="default.save_form">
                <nebri-dictionary id="dictionary1" fields="[[fields1]]"></nebri-dictionary>
                <nebri-dictionary id="dictionary2" fields="[[fields2]]" disabled></nebri-dictionary>
            </nebri-form>
        </template>
        <script>
            Polymer({
                is: "dictionary-test",
                behaviors: [NebriElement],
                properties: {
                    fields1: {
                        type: Array,
                        value: [
                            {'type': 'string', 'label': 'A String', 'value': 'bar'},
                            {'type': 'integer', 'label': 'An Integer', 'placeholder': '6'},
                            {'type': 'boolean', 'label': 'A Checkbox', 'value': true}
                        ]
                    },
                    fields2: {
                        type: Array,
                        value: [
                            {'type': 'float', 'label': 'A Float', 'value': '5.3'},
                            {'type': 'email', 'label': 'An Email', 'placeholder': 'em@ail.com'},
                            {'type': 'zipcode', 'label': 'A Zipcode', 'placeholder': '12345'}
                        ]
                    }
                }
                });
        </script>
    </dom-module>

.. image:: /img/inputs/dictionary-example.png