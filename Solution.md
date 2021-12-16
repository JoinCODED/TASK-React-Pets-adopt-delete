### Adopting a Pet!

1. Create a new adopt button under our pet button that removes the pet from the list.

```javascript
<button type="button" class="btn btn-info">
  Adopt
</button>
```

2. Since our pets list now changes, we need to create a state for it and replace our `props.pets` that we maps to our new state.

```javascript
const [petsData, setPetsData] = useState(props.pets);
const pets = petsData
  .filter(
    (pet) =>
      pet.name.toLowerCase().includes(query.toLowerCase()) &&
      pet.type.includes(type)
  )
  .map((pet) => <PetItem key={pet.id} pet={pet} />);
```

3. Create a method called `handleAdopt` that takes `petId` as an arguemnt and filters our pets list state to not have this pet.

```javascript
const handleAdopt = (petId) =>
  setPetsData(petsData.filter((pet) => pet.id !== petId));
```

4. Pass this method to `PetItem` and pass it to the `onClick` method of our new button.

```javascript
<PetItem key={pet.id} pet={pet} handleAdopt={handleAdopt} />
```

```javascript
<button
  type="button"
  class="btn btn-info"
  onClick={() => props.handleAdopt(pet.id)}
>
  Adopt
</button>
```

### Challenge

1. We will use `window.confirm` which show a dialog with `yes` and `no` buttons, in our adopt button:

```javascript
<button
  type="button"
  class="btn btn-info"
  onClick={() => {
    if (window.confirm('Are you sure you want to adopt this pet?')) {
      props.handleAdopt(pet.id);
    }
  }}
>
  Adopt
</button>
```
