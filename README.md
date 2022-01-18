### Adopting a Pet!

1. Create a new adopt button under our pet button in `PetItem.js` that removes the pet from the list.
2. Since our pets list now changes, we need to create a state for it that holds our list in `PetList.js` and replace the prop `pets` that we maps to our new state.
3. In `PetList.js` create a method called `handleAdopt` that takes `petId` as an arguemnt and filters our pets list state to not have this pet.
4. Pass this method to `PetItem` and pass it to the `onClick` method of our new button.

### Challenge

1. When clicking on adopt, show an alert to the user where he have to confirm his adoption or cancel it.
