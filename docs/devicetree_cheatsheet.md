# ZMK Devicetree Cheatsheet (for Java Programmers)

## General Concepts

| ZMK Term       | What It Means                          | Java Analogy                                |
| -------------- | -------------------------------------- | ------------------------------------------- |
| **Node**       | A hardware config block                | An object (with properties)                 |
| **Property**   | A named setting inside a node          | A field inside an object                    |
| **`&node`**    | A reference to another node            | Passing an object reference (like `chord0`) |
| **Overlay**    | A file that overrides or adds to nodes | A subclass or patch                         |
| **Devicetree** | A structured config for all hardware   | A configuration graph or metadata class     |

## Example ZMK Code Block

```dts
&chord_0 {
  bindings = <&kp E>;
  chord-keys = <0 1>;
};
```

### Translation:

> The `chord_0` node is a named configuration. It says: “when key 0 and 1 are pressed, treat it as an `E` keypress.”

## Common Keywords

| ZMK Keyword  | Meaning                                       |
| ------------ | --------------------------------------------- |
| `compatible` | Declares what kind of node it is              |
| `bindings`   | What happens when the key or chord is pressed |
| `chord-keys` | Which keys must be pressed together           |
| `label`      | A human-readable name                         |
| `zmk,keymap` | Tells ZMK this is a keymap node               |
| `&kp`        | Reference to a keypress behavior              |

## Typical Structure

ZMK configs follow a hierarchy:

```dts
keymap {
    base_layer {
        bindings = <&chord_0 &chord_1 &none>;
    };
};

&chord_0 {
    bindings = <&kp A>;
    chord-keys = <0 1>;
};
```

This means: when keys 0 and 1 are pressed, send an `A`.

## Overlay vs. Conf vs. Keymap

| File        | Purpose                                         |
| ----------- | ----------------------------------------------- |
| `*.overlay` | Defines new nodes or modifies hardware behavior |
| `*.conf`    | Enables ZMK features (tap dance, mod-tap, etc.) |
| `*.keymap`  | Defines the actual keys and chords              |


