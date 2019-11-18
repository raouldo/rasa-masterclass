## meeting room book happy path
* greet
 - utter_how_can_i_help
 * book_meeting_room{"facility_type": "meeting room", "equipment": "video projector"}
  - action_facility_book
  - slot{"room_name": "Actor"}
* thanks
  -utter_goodbye

## meeting room book + equipment
<!-- add the story here : in this story, the assistant should ask for the equipment to book -->

## happy path
* greet
  - utter_greet
* mood_great
  - utter_happy

## sad path 1
* greet
  - utter_greet
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* affirm
  - utter_happy

## sad path 2
* greet
  - utter_greet
* mood_unhappy
  - utter_cheer_up
  - utter_did_that_help
* deny
  - utter_goodbye

## say goodbye
* goodbye
  - utter_goodbye
