# PowershellMagic
Powershell Oneliners

## DFS

### DFS Preseeding
This robocopy command is the command recommended by Microsoft for when you need to preseed a share that's going to be part of a DFS replicated folder
````
robocopy "\\server1\share" "E:\LocalFolder" /e /b /copyall /r:6 /w:5 /MT:64 /xd DfsrPrivate /tee /log:C:\Logs\preseed.log /v
````

### DFS Replication Status
````powershell
Get-DfsrState -ComputerName "server1" | Format-Table FileName,UpdateState,Inbound,Source* -Auto -Wrap
````
