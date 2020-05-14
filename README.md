# monodevelop-versioncontrol-bin
Version Control for MonoDevelop - compiled binaries

(Re)build instructions:

Clone https://github.com/mono/monodevelop.git#release-7.8
Open solution

Unload Core/MonoDevelop.Ide 
Unload Addins/MonoDevelop.Debugger/MonoDevelop.Debugger
Unload Addins/MonoDevelop.SourceEditor

Unload contrib/Mono.Addins/Mono.Addins.CecilReflector
Unload Addins/VBNetBinding/VBNetBinding

Copy MonoDevelop.Ide.dll from installed location (AUR monodevelop-bin - /usr/lib/monodevelop/bin/) to main/build/bin/
Copy MonoDevelop.Debugger.dll from installed location (AUR monodevelop-bin - /usr/lib/monodevelop/AddIns/MonoDevelop.Debugger/) to main/build/AddIns/MonoDevelop.Debugger/
Copy MonoDevelop.SourceEditor.dll from installed location (AUR monodevelop-bin - /usr/lib/monodevelop/AddIns/DisplayBindings/SourceEditor/) to main/build/AddIns/DisplayBindings/SourceEditor/

Extract /usr/lib/monodevelop/AddIns/VersionControl/libgit2* from Debian monodevelop-versioncontrol package availble here: https://packages.debian.org/stretch/monodevelop-versioncontrol to main/external/libgit2/build/ (because this doesn't build)

Config: ReleaseGnome.
Ensure gtk-sharp-3 NOT installed in system as this breaks build

Build Core/MonoDevelop.Core
Build Addins/VersionControl
Build Addins/ChangeLogAddIn

rm main/build/AddIns/VersionControl/&ast;.pdb
rm main/build/AddIns/ChangeLogAddIn/&ast;.pdb

