scala
=====

scala のフォーマットには scalariform が使えます。

formatterPreferences.properties
--------------------------------

[scalariform](https://github.com/mdr/scalariform) で使用できるフォーマットです。

### sbt

project/formatterPreferences.properties に保存して [sbt-scalariform](https://github.com/sbt/sbt-scalariform) project.sbt で

```
com.typesafe.sbt.SbtScalariform.ScalariformKeys.preferences := {
  scalariform.formatter.preferences.PreferencesImporterExporter.loadPreferences("project/formatterPreferences.properties")
}
```

とするとコンパイル時にフォーマットしてくれます。

### eclipse scala-ide

Preference -> Scala/Editor/Formatter で `formatterPreferences.properties` を Import できます。

Preference -> Scala/Editor/Save Actions で Autoformatting をチェックしましょう。

### IntelliJ IDEA

https://plugins.jetbrains.com/plugin/7480?pr=
https://github.com/thesamet/scalariform-intellij-plugin

が使えるかも？ ( TODO: 確認して追記してください )

### sublime text

[ScalaFormat](https://github.com/timonwong/ScalaFormat) プラグインを利用できます。プラグインパッケージをインストールしたら、

Preference -> Package Settings -> ScalaFormat -> Settings - User から

```
{
  // java の exe ファイルのパス
  "java_executable":"C:\\Program Files\\Java\\jdk1.7.0_25\\jre\\bin\\java.exe",
  // formatterPreferences.properties を json にしたもの
  "scalariform":{
    "alignParameters":true,
    "formatXml":false,
    "preserveDanglingCloseParenthesis":false,
    "spaceInsideBrackets":false,
    "indentWithTabs":false,
    "spaceInsideParentheses":false,
    "multilineScaladocCommentsStartOnFirstLine":false,
    "alignSingleLineCaseStatements":true,
    "compactStringConcatenation":false,
    "placeScaladocAsterisksBeneathSecondAsterisk":false,
    "indentPackageBlocks":true,
    "compactControlReadability":false,
    "spacesWithinPatternBinders":true,
    "alignSingleLineCaseStatements.maxArrowIndent":40,
    "doubleIndentClassDeclaration":true,
    "preserveSpaceBeforeArguments":false,
    "spaceBeforeColon":false,
    "rewriteArrowSymbols":false,
    "indentLocalDefs":false,
    "indentSpaces":2
  }
 
}
```

を設定してください。
