/*
This Function returns subfolder Ids of a structured Directories System
e.g. A Folder that contains clients and every client have a folder obligations.
it has the pontentional to exlude index caracter with excar
*/

function structureSubfolderIds(rootID,subdirName,exIndex) {
  var IDs=[];
  var rootDir = DriveApp.getFolderById(rootID).getFolders();
 
  while(rootDir.hasNext()){
    var curFolder = rootDir.next();
    var folderName  = curFolder.getName();
   
    if(folderName.indexOf(exIndex) != 0)
      if(curFolder.getFoldersByName(subdirName).hasNext())
         IDs.push(curFolder.getFoldersByName(subdirName).next().getId()); //add ID to IDs Array
      else
        Logger.log('WARNING:Folder '+folderName+' does not contain '+subdirName);
  }
  
  return IDs;
}

function test(){
  var IDs = structureSubfolderIds('1viQJuq2qYx02mJ1P-iAdBQzCFzz1WSh4','_ΛΟΙΠΑ ΕΝΤΥΠΑ','_');
  
  fLen = IDs.length;
  
  for (i = 0; i < fLen; i++) {
    Logger.log(IDs[i]);
  }
}
