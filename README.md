# TestLite
LabVIEW based test framework, implements features kind like TestStand but not as powerful as TestStand. As it's name stated, it's lite compare to TestStand. The framework implements basic test software architecture and also provide plugin mechanism let developer extend system function without changing framework code.  

#### Ddependencies:
* OpenG Variant Configuration File Library
  > Install from VIPM repository: [vipm://oglib_variantconfig?repo_url=http://www.jkisoft.com/packages](vipm://oglib_variantconfig?repo_url=http://www.jkisoft.com/packages)

## Getting Started
---
#### Create Test Project
* Clone code: git clone https://github.com/Tom-Lu/TestLite.git
* Create new LabVIEW project for you test project
  > This is the main workspace for your test project, you will maintain and organize all your test project related stuff under this LabVIEW project. 
* Add TestLite Core folder to you project as auto-populating folder
* Add new class as main test project class and change inheritance make TestLite/Core/Project.lvclass as parent of your project class.
* Save your LabVIEW project and classes.
* Open and run the TestLite/Core/Editor.lvclass/UI.vi or run prebuild executable file "TestLite Editor.exe".
  > TestLite Editor is the test sequence editor for the framework, it's similar to TestStand's sequence editor except don't have interactively execution and debug ability.
* Click "New" button in the editor gui and select the test project class you created, now you create your first TestLite test project.
* After you have your TestLite project created, you can add steps and change project or step properties.
Three different kind of steps supported:
  * UI Step
    > UI Function such as message display, image display(jpg and png), batton selection, text input.
  * VI Step
      > Step for call LabVIEW VIs, could be your project class memebers or standalone VIs.
  * EXE Step
      > Step for call executable

#### Run Test Project
* Open and run the TestLite/Core/Application.lvclass/Main UI.vi or run prebuild executable file "TestLite Executor.exe".
* Load your test project through menu "System -> Load Project".
  > TestLite embeded with one project loader plugin which supports load project manually or automatically from specified location. The project loader can be extended to achieve something like list of available projects let user to chose. 

* Click "START" button in the executor UI to run your test project.
  > It's also possible to implements features like test execution trigger through external signal like DIO or other DUT detect method.