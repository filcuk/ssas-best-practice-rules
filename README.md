## Differences compared to MS BPA rules

```bash
diff --git a/BPARules.json b/microsoft/BestPracticeRules/BPARules.json
```

```git
@@ -593,11 +593,11 @@
     "ID": "DATECOLUMN_FORMATSTRING",
     "Name": "[Formatting] Provide format string for \"Date\" columns",
     "Category": "Formatting",
-    "Description": "Columns of type \"DateTime\" that have \"Month\" in their names should be formatted as \"dd/mm/yyyy\".",
+    "Description": "Columns of type \"DateTime\" that have \"Month\" in their names should be formatted as \"mm/dd/yyyy\".",
     "Severity": 1,
     "Scope": "DataColumn, CalculatedColumn, CalculatedTableColumn",
-    "Expression": "Name.IndexOf(\"Date\", \"OrdinalIgnoreCase\") >= 0 \r\nand \r\nDataType = \"DateTime\" \r\nand \r\nFormatString <> \"dd/mm/yyyy\"",
-    "FixExpression": "FormatString = \"dd/mm/yyyy\"",
+    "Expression": "Name.IndexOf(\"Date\", \"OrdinalIgnoreCase\") >= 0 \r\nand \r\nDataType = \"DateTime\" \r\nand \r\nFormatString <> \"mm/dd/yyyy\"",
+    "FixExpression": "FormatString = \"mm/dd/yyyy\"",
     "CompatibilityLevel": 1200
   },
   {
@@ -648,7 +648,7 @@
     "Category": "Formatting",
     "Severity": 2,
     "Scope": "Measure",
-    "Expression": "DataType == DataType.Int64 and not FormatString.Contains(\"$\") and not FormatString.Contains(\"%\") and not (FormatString = \"#,0\" or FormatString = \"#,0.0\")",
+    "Expression": "not FormatString.Contains(\"$\") and not FormatString.Contains(\"%\") and not (FormatString = \"#,0\" or FormatString = \"#,0.0\")",
     "FixExpression": "FormatString = \"#,0\"",
     "CompatibilityLevel": 1200
   },
```