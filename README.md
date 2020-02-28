# ScriptableAnimator
Generate a Unity script which allows you to access your Animator values without having to use string variables.

### Getting Started
1. Import the ScriptableAnimator.cs into your Unity Project
2. Open up your Animator in the Inspector and hit the "Generate Script" Button.
     This creates a two new Scripts in the Folder "Assets/Generated/Animator" A State.cs, which is just a helper class, 
     and a class with the name of your AnimatorController like "PlayerAnimator.cs"
3. Add this PlayerAnimator Script to the same Object the Anomator is attached to
4 Done!

### Using the Script

Store a Reference in the Script you wan't to use the Animator
```
private PlayerAnimator animator;

  private void Awake()
  {
    animator = GetComponent<PlayerAnimator>();
  }
```

#### Setting a Parameter
```
// set a Trigger
animator.Parameter.SetJump();
// set a value
animator.Parameter.Running = true;
```

#### Directly calling a Animation
The scripted Animator stores the animations in the same layered way the animator does, so if you want to call a animation on your "Base" Layer
you would call `animator.base.attack.Play();`
If you use substates you could start the substate with the entrystate exactly the same by calling `animator.base.substate.Play();`
or play a childstate by calling `animator.base.substate.child.Play();`
