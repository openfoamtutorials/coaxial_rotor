# coaxial_rotor

This utilizes the OpenFOAM rotorDisk model, which is a simple BEM on cells arranged in a disk, to simulate coaxial rotors.

To get proper power output and rotation direction, the source requires a little bit of modification. Change and compile via:
sudo -s
cp src/new.C $FOAM_SRC/fvOptions/sources/derived/rotorDiskSource/rotorDiskSourceTemplates.C
cd $FOAM_SRC/fvOptions
wmake
exit

You can see the difference between the new and old source via:
diff src/new.C src/original.C

Mesh and run the simulation via:
./run.sh

You can start over the simulation by deleting generated files via:
./clean.py

When viewing results, when looking at Z direction (through the thin of the wedge) it is important to use the cell-based visualization, rather than point-based. Point-based for some reason does not color the directions properly.

