### Batch-of-Windows
+ 文件类型：.bat .cmd
+ 程序作用：从多层文件夹中提取出具有某一特点的文件，并复制到<b>resulePath</b>路径中
+ 问题描述：在目录<b>H:\gdg\47788321\</b>下有几十个文件夹，每个文件夹下面都具有相同的结构多层目录，文件名全相同

'''
"@echo off
SETLOCAL ENABLEDELAYEDEXPANSION
SET /a x=0
set resulePath=H:\gdg\47788321\videos
FOR /r %%i IN (.) DO (
	IF EXIST %%i\16\audio.mp3 (
    		SET /a x+=1
        		XCOPY %%i\16\audio.mp3  %resulePath%\audio_!x!.mp3 /y  
        		REN "audios\audio.m4s" "audio_!x!.m4s"	 
		echo x
   	 )
)
ENDLOCAL
'''
