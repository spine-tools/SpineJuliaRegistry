# SpineJuliaRegistry

>[!IMPORTANT]
> This repository is obsolete! Both [SpineOpt](https://github.com/spine-tools/SpineOpt.jl) and [SpineInterface](https://github.com/spine-tools/SpineInterface.jl) are now available through general Julia registry.

Julia package registry for the Spine project.


## Updating the versions in the registry

**NEVER update the registry files manually!**
Instead, the easiest way to update the registry is by using the
[LocalRegistry.jl](https://www.juliapackages.com/p/localregistry) package,
follow the instructions for its installation in its README.

Updating the versions of the included packages is essentially done according to the
*Register a New Version of a Package* instructions in the
[LocalRegistry.jl](https://www.juliapackages.com/p/localregistry) README.
First you need to be in a Julia environment with *LocalRegistry* installed
```julia
using LocalRegistry
```
You can see the versions of the packages contained within this registry under
`S\\<PACKAGE_NAME>\\Versions.toml`, and you cannot register a new version
of a package unless its version is higher than any registered one.
Versions of Julia packages are contained in their respective `Project.toml` files, e.g.:
```julia
name = "SpineOpt"
uuid = "0d8fc150-4032-4b6e-9540-20efcb304861"
authors = ["Spine Project consortium <spine_info@vtt.fi>"]
version = "0.6.14"
```
Then, you want to `develop` the latest version of the package you want to register
into said environment
```julia
using Pkg
Pkg.develop("<path_to_desired_package>")
```
And finally, you register the `develop` version of the package
```julia
register("<name_of_package>", registry="<path_to_local_clone_of_SpineJuliaRegistry>")
```

As long as your only updating the versions of the packages included in the registry,
the registry information can be omitted from the `register` function.
*(Not 100% sure where this information is deduced from, probably from `Project.toml`?)*


## Adding a new package

For now, please refer to the *Register a Package* section of the
[LocalRegistry.jl](https://www.juliapackages.com/p/localregistry) README.


## Acknowledgements

<center>
<table width=500px frame="none">
<tr>
<td valign="middle" width=100px>
<img src=https://european-union.europa.eu/themes/contrib/oe_theme/dist/eu/images/logo/standard-version/positive/logo-eu--en.svg alt="EU emblem" width=100%></td>
<td valign="middle">This work has been partially supported by EU project Mopo (2023-2026), which has received funding from European Climate, Infrastructure and Environment Executive Agency under the European Union’s HORIZON Research and Innovation Actions under grant agreement N°101095998.</td>
<tr>
<td valign="middle" width=100px>
<img src=https://european-union.europa.eu/themes/contrib/oe_theme/dist/eu/images/logo/standard-version/positive/logo-eu--en.svg alt="EU emblem" width=100%></td>
<td valign="middle">This work has been partially supported by EU project Spine (2017-2021), which has received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement No 774629.</td>
</table>
</center>
