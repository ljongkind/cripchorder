# ZMK Devicetree Cheatsheet (for Java Programmers)

## General Concepts

| ZMK Term         | What It Means                            | Java Analogy                                 |
|------------------|-------------------------------------------|-----------------------------------------------|
| **Node**         | A hardware config block                   | An object (with properties)                   |
| **Property**     | A named setting inside a node             | A field inside an object                      |
| **`&node`**      | A reference to another node               | Passing an object reference (like `chord0`)   |
| **Overlay**      | A file that overrides or adds to nodes    | A subclass or patch                           |
| **Devicetree**   | A structured config for all hardware      | A configuration graph or metadata class       |

---

## Example ZMK Code Block

```dts
&chord_0 {
  bindings = <&kp E>;
  chord-keys = <0 1>;
};
