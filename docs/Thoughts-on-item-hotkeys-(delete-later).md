Three things should be implemented as part of this.

1) Persisting loaded items between sessions.
2) Saving/Loading item scenes using the UI.
3) Loading items using hotkeys.

# Glossary

* `Internal Item`: Item within the "Items" folder (GIF, PNG or animated PNG folder).
* `External Item`: Item outside the "Items folder (GIF, PNG or animated PNG folder).

# Basic item persistence between VTS sessions

* Items should be saved at their respective positions, including items attached to the Live2D model. 
* Meaning if VTS if quit with items in the scene, they will be automatically loaded again when VTS is started.
* This should only happen if `"Remember Scene"` is active in the VTube Studio config.
* This should work for external and internal items.
* This functionality is completely unrelated to item hotkeys and saving/loading item scenes.

# Saving Item Scenes

* Users should be able to save the current state of the items in the scene. The idea is that you can load internal and external items into the scene and then use a "save" functionality somewhere on the UI.
  * This UI has the option to include or exclude items attached to the model.
  * This UI shows a list of all items that will be saved.
* Each item is identified by its ID, which is its filename. No two items should have the same filename. For animated PNG folder items, the filename is the folder name.
* For each item, the saved properties are position, rotation and scale. For items attached to the model, the exact model attachment point is saved.
* Other saved properties: Scene order, smoothing value and "censored" state.
* If the scene is later loaded and a different model is active, items attached to the model won't be loaded. If this happens, failure to load the items will be logged appropriately.
* There will be a UI to list saved item scenes. This UI will also allow you to delete item scenes, show their contents or rename them.
* Item scenes will be saved in a folder called "Scenes". This folder will contain files called `"<scene-name-ascii>.scene.json"`.
* All items will be referenced as filenames in the "Items" folder. This means that `external items` will automatically have to be copied to the "Items" folder when a scene is saved with them included.
  * Thinking about it now, I think it makes sense to automatically save any external items in the "Items" folder the moment it is loaded into the scene.

# Loading Item Scenes

The previously saved scenes can be loaded via a UI (or hotkeys, see below). The most complex point here is how to deal with items that appear in multiple scenes or how to deal with partially loaded/unloaded scenes. 

Let's assume the scene is empty and we have the the following scenes saved.

* Scene A
  * Item 1
  * Item 2
* Scene B
  * Item 2
  * Item 3

Then, scene A is loaded (using hotkey). Item 1 and 2 appear at the saved positions. 

Then, scene B is loaded (using hotkey). Item 3 is loaded and item 2 is moved to the respective position stored as part of scene B.

Then, scene A is loaded again (using hotkey). This moves item 2 back to the position stored in scene A.

Then, scene A is loaded again (using hotkey). Because all items of scene A are in the exact position recorded in scene A, this will be interpreted as an "unload" event. All items of scene A will be unloaded.

If you load scene A and move one item and then load scene A again, the item will move back to the position it was in for scene A. Scenes will only be "unloaded" if you trigger them while all their included items are at the exact same spot as they are in the current scene state.

# Scene Item Ordering

The order of items is saved with the scene. This means that a scene could be loaded but some item order spots are already taken. In that case, the order of the items will be shifted up. If there are no spots above, it the order will be shifted down instead. If there are no spots left in the scene, no further items will be loaded and the scene may be incomplete.

# Hotkeys

There will be four new hotkey types:

* `Load Item Scene`: Loads the given item scene (item scenes are identified by their name, which must be unique)
* `Unload all items`: Instantly removes all items from the scene
* `Quicksave Items`: Saves the current state of all items in the scene into quicksave slot
* `Quickload Items`: Loads the current state of all items in the scene from quicksave slot






