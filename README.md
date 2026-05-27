Init EAS
```bash
eas init
```

Make sure that precompiled modules are enabled
```bash
eas env:create --name EXPO_USE_PRECOMPILED_MODULES --value 1 --visibility plaintext
```

Launch build
```bash
eas build --platform ios
```

The build will fail with an error like this one:
```
Runtime version mismatch:
- Runtime version calculated on local machine: 05ab7764b4ffc8882b799e55ad37d57ab14b2139
- Runtime version calculated on EAS: bd5cbc43db42ec625548dfecce8060e369fe8065

This may be due to one or more factors:
- Differing result of conditional app config (app.config.js) evaluation for runtime version resolution.
- Differing fingerprint when using fingerprint runtime version policy. If applicable, see fingerprint diff below.

This would cause any updates published on the local machine to not be compatible with this build.
Difference between local and EAS fingerprints:
[
 {
  "op": "added",
  "addedSource": {
   "type": "dir",
   "filePath": "ios",
   "reasons": [
    "bareNativeDir"
   ],
   "hash": null
  }
 },
 {
  "op": "changed",
  "beforeSource": {
   "type": "dir",
   "filePath": "node_modules/react-native-reanimated",
   "reasons": [
    "rncoreAutolinkingIos"
   ],
   "hash": "fb8e1ddff024a6eb4224767acde16e5c4d490610"
  },
  "afterSource": {
   "type": "dir",
   "filePath": "node_modules/react-native-reanimated",
   "reasons": [
    "rncoreAutolinkingIos"
   ],
   "hash": "60a60224372ca423f86f973670440bd3ac7c68fb"
  }
 },
 {
  "op": "changed",
  "beforeSource": {
   "type": "dir",
   "filePath": "node_modules/react-native-worklets",
   "reasons": [
    "rncoreAutolinkingIos"
   ],
   "hash": "e7b27e6c73923e9dd4f0f7f035a5a91f359d4cd9"
  },
  "afterSource": {
   "type": "dir",
   "filePath": "node_modules/react-native-worklets",
   "reasons": [
    "rncoreAutolinkingIos"
   ],
   "hash": "80467424ef1876417b176a2a24337c3a17b84b51"
  }
 }
]
```