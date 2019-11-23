# Tutorial: Generation of C# Library Stubs

As a result of running [the *specification-side adapter*](https://github.com/Zeman-Dalibor/DotNetLibraryExporter),
you should have an XML file, which describes the library stubs. With this done, you can continue
to another phase of the process - using this plugin for stubs generation.

First, you should have the plugins installed. You can do it by navigating through `File` to
`Settings` to `Plugins` to `Marketplace` where you can search for the plugin `StubsGenerator`
and install it. Then, install also plugins `LangDoc`, `CsBaseLanguage` and `CsStubsGenerator`,
in this order.

Now, please, restart your MPS.

When the previous is ready, create a new solution-like project (via `File`, `New`, `Project`,
`Solution project`).

Right-click the created solution in the created project. Selecting the `Generate Stubs` option
should result in a file-choosing dialog which you utilize for selection of the XML file you have
generated by the *specification-side adapter*.

When the XML file is selected, automatic generation starts and on its end, you should see the
generated stubs under the selected solution. Note that this process might take a while when the
library is large (e.g. the stubs generation for the C# standard library lasts several seconds).

Now you can rebuild the solution in order to be able to use the stubs in your models.

Note that, when using the C# base language and creating a model in which you intend to use
the generated stubs, you should set up a dependency on the CsBaseLanguage and on the **models**
containing the generated stubs you desire to use. You cannot set up a dependency on the whole
solution with the stubs, you must select individual models (e.g. on the `System` model of the C#
standard library, not on the whole `CsStdLibrary` solution).