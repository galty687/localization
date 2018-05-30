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


常用宏代码
===============

统计字数时包含标点符号

.. code-blocl:: vba

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


