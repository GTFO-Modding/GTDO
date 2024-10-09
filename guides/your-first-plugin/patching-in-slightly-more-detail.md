# Patching in slightly more detail

This is a very basic summary of patching. See the [harmony documentation](https://harmony.pardeike.net/articles/patching.html) for more details.

#### Why patching

Typically, when making a plugin, developers will want to change how something in the base game behaves. Of course, in order to change the normal behavior we need to know what piece(s) of code in the base game determine that behavior so that we can target them with a patch. This means that part of the challenge of making a plugin is determining which method(s) to patch in the first place! If you're unsure how to go about determining which methods to target consider asking in our [Discord Server](https://discord.com/invite/rRMPtv4FAh).

### Patching

The two basic kinds of patches are Prefix and Postfix patches. Both of these target some original method in the game's code in the same way through the `[HarmonyPatch(...)]` attribute (though there are also more complicated ways to determine which method they target).

#### Postfix Patches

Postfix patches use the `[HarmonyPostFix]` attribute. Postfix patches run after the original method. As with any patch this allows you to run any code you want at this point, but also importantly, this can let you alter the normal return value of that method.

#### Prefix Patches

Prefix patches use the `[HarmonyPreFix]` attribute. Prefix patches run before the original method. They can alter the arguments of the original method before that method runs. They can also control whether or not to skip the original method completely.

Unfortunately, a more complicated kind of patch (Transpiler patches) which offers some unique benefits doesn't quite work with how GTFO is compiled.
