==================
Word 宏
==================

学习目标
===============

#. 熟悉和了解基本的Word对象及VBA语法
#. 录制宏并进行宏编辑
#. 编写简单的宏命令实现操作自动化
#. 制作Word工具条

课程演示
==========

#. 录制宏实现双语对照格式
#. 直接编写宏实现双语对照


课程素材

使用Word随机文本函数自动生成

::

    =rand(4,4)


手工操作简要步骤：

#. 选中文本，将文字转为表格
#. 添加一列
#. 将原文列的文字复制到新增加的列当中
#. 将原文列的文字隐藏
#. 使用CAT工具翻译后，再恢复原文列
#. 取消隐藏文字
#. 将表格转为文字


录制宏：


编写宏代码

 .. code-block:: vba

    Sub CopyHidePast()
    '
    ' CopyHidePast Macro
    '
    '
    Dim n As Long
    n = 1

    While n < ActiveDocument.Paragraphs.Count


        ActiveDocument.Paragraphs(n).Range.Select
        Selection.Copy
        With Selection.Font
            .Hidden = True
        End With
        
        Selection.EndKey unit:=wdLine
        Selection.TypeParagraph
        Selection.TypeParagraph
        Selection.Paste
        
        n = n + 4

    Wend

    End Sub



常用宏代码
===============

统计字数时包含标点符号

 .. code-block:: vba

    Sub count_space()
        Selection.WholeStory
        Selection.Find.ClearFormatting
        Selection.Find.Replacement.ClearFormatting
        With Selection.Find
            .Text = "(['""\,\.\;\?\!/\-\':+])[ ^13]"
            .Replacement.Text = " " & "\1" & " "
            .Forward = True
            .Wrap = wdFindContinue
            .MatchWildcards = True
        End With
        Selection.Find.Execute Replace:=wdReplaceAll
        MsgBox ActiveDocument.ComputeStatistics(statistic:=wdStatisticWords, IncludeFootnotesAndEndnotes:=True) & "words"
        ActiveDocument.Undo 1
    End Sub

将doc转为docx

 .. code-block:: vba

    Sub SaveAllAsDOCX()
        Dim strFilename As String
        Dim strDocName As String
        Dim strPath As String
        Dim oDoc As Document
        Dim fDialog As FileDialog
        Dim intPos As Integer
        Set fDialog = Application.FileDialog(msoFileDialogFolderPicker)
        With fDialog
            .Title = "Select folder and click OK"
            .AllowMultiSelect = False
            ..InitialView = msoFileDialogViewList
            If .Show <> -1 Then
                MsgBox "Cancelled By User", , "List Folder Contents"
                Exit Sub
            End If
            strPath = fDialog.SelectedItems.Item(1)
            If Right(strPath, 1) <> "\" Then strPath = strPath + "\"
        End With
        If Documents.Count > 0 Then
            Documents.Close SaveChanges:=wdPromptToSaveChanges
        End If
        If Left(strPath, 1) = Chr(34) Then
            strPath = Mid(strPath, 2, Len(strPath) - 2)
        End If
        strFilename = Dir$(strPath & "*.doc")
        While Len(strFilename) <> 0
            Set oDoc = Documents.Open(strPath & strFilename)
            strDocName = ActiveDocument.FullName
            intPos = InStrRev(strDocName, ".")
            strDocName = Left(strDocName, intPos - 1)
            strDocName = strDocName & ".docx"
            oDoc.SaveAs FileName:=strDocName, _
                FileFormat:=wdFormatDocumentDefault
            oDoc.Close SaveChanges:=wdDoNotSaveChanges
            strFilename = Dir$()
        Wend
    End Sub

Title Case 

 .. code-block:: vba

    Sub TitleCase()
        Dim lclist As String
        Dim wrd As Integer
        Dim sTest As String

        ' list of lowercase words, surrounded by spaces
        lclist = " of the by to this is from a "

        Selection.Range.Case = wdTitleWord

        For wrd = 2 To Selection.Range.Words.Count
            sTest = Trim(Selection.Range.Words(wrd))
            sTest = " " & LCase(sTest) & " "
            If InStr(lclist, sTest) Then
                Selection.Range.Words(wrd).Case = wdLowerCase
            End If
        Next wrd
    End Sub

 .. note::

    在 lclist中增加不需要大写的单词时，一定要记得后面加一个空格，否则无法识别。



更多常用VBA地址：`TT4T - Word Macros for Translators <http://necco.ca/dv/word_macros.htm>`_
