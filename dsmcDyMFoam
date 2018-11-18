#include "fvCFD.H"
#include "dynamicFvMesh.H"
#include "dsmcCloud.H"

int main(int argc, char *argv[])
{
    #include "setRootCase.H"
    #include "createTime.H"
    #include "createDynamicFvMesh.H"

    Info<< nl << "Constructing dsmcCloud " << endl;

    dsmcCloud dsmc("dsmc", mesh);

    Info<< "\nStarting time loop\n" << endl;

    while (runTime.loop())
    {
        Info<< "Time = " << runTime.timeName() << nl << endl;

        mesh.update();

        dsmc.evolve();

        dsmc.info();

        runTime.write();

        Info<< nl << "ExecutionTime = " << runTime.elapsedCpuTime() << " s"
            << "  ClockTime = " << runTime.elapsedClockTime() << " s"
            << nl << endl;
    }

    Info<< "End\n" << endl;

    return 0;
}
