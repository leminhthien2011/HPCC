# HPCC
This includes tips in HPCC
s -
#########dO WE NEED TO BE CLEARER, THIEN?
fin +expHPCC Basic
1/ cd /mnt/home/lethien1/main/tutorial (set directory)
Even faster: 
cd $HOME/main/tutorial ($Home replace /mnt/home/lethien1/)



2/  (install package Hpcc)

3/ mkdir -p ~/R/library
Rscript -e "install.packages('myPackage', lib='~/R/library', contriburl=contrib.url('http://cran.r-project.org/'))" 
(Install package)


4/ module load R, then
export R_LIBS_USER=~/R/library
each time once need to check on development node.


5/ R
 Can also do: 
module purge
module load GCC/7.3.0-2.30  OpenMPI/3.1.1 R/3.5.1-X11-20180604



rm *.job

6/ module list : check available software


7/ Install package: 
mkdir -p ~/R/library
Rscript -e "install.packages('myPackage', lib='~/R/library', contriburl=contrib.url('http://cran.r-project.org/'))"


8/ Move a file  
 mv /mnt/home/lethien1/main/testing.R /mnt/home/lethien1/main/working/


9/sbatch -a 1-36 mainrun.sb- (submit job)

Managing job: 

Check in queue: squeue -l -u $lethien1
or          sq 
or           qs   for more inform
Also     sview

Show job with ID:  show job 8929
Cancel Job with ID: scancel 8929
MATLAB
$ matlab -nodisplay -r "test"   (INTERACTIVELY)
$ sbatch runmatlab.sb   (Batch Run)

Submit batch job Matlab 
python run_job.py

10/ Download File in a systematic way
mkdir test(create a folder name test)
cp Networkp_n_s0_tuning_nrepeat_1000_500_4_*_16.txt test (all file with number as *)
cd ./test/ (see waht we got in test)
cd ../ (back to home page)
rm Datap*.txt( delete all file as Datap...txt)
  add a number in array
arr=( "${arr[@]}" "new_element" )
Create a sequence: myseq =  ($(seq 70 5 210))
 10b/ Create a new folder
mkdir Newfolder

10c/ insert text: i
quit: esc, 
then :wq quit and save
:q! quit and no save any changes
:q quit and don't save





10/ rm -r flags/ (remove flags before submit a new job)

generate cases for a new run
./generate_cases.sh

permission to execute .sh file
chmod +x ./generate_cases1.sh

11/ getexample (to see what example available)

12/ getexample MATLAB_basic
(Say doing for Matlab)

13/  cd MATLAB_basic/

14/ ls to see output

15/ vim README

16/ matlab -nodisplay -r "test"

17/ Rename File
mv oldname newname

18/ Rename File with loop
for f in TestTuningvaluesp_n_nrepeat_250_500_*.mat; do mv "$f" "$(echo "$f" | sed s/TestTuningvaluesp_n_nrepeat_250_500_/TestTuningvaluesp_n_nrepeat_250_500_6_/)"; done

19/ 
Rename File with loop but some notation involved in the file
 for f in TestTuningvaluesp_n_nrepeat_1000_250_6_*.mat; do mv "$f" "$(echo "$f" | sed s/TestTuningvaluesp_n_nrepeat_1000_250_6_\\*/TestTuningvaluesp_n_nrepeat_1000_250_6_/)"; done
Notice that this case Testing Tuningfile get *before nrepeat, we need \\ to deal with

20/
Find all .R files:
find  -type f -name "*.R"
find -name "*.R"
find -name "*.R"

21/ copy file   cp file1 file2

22/ vim abc choose "tab" key then "tab"
 again, it will show the total number of files in the shape "abc....."

23/ Count nulsmber of file content a name or extension, say count number all "*.input"
ls -dq *.input | wc -l

24/Cancel all jobs submitted
scancel --user=lethien1

25/ Check flags folder, cd flags
then ls and vim some of them.
go back   cd..

26/ ls -lrth : check most updated job.

27/ pwd to know where we are

28/ cd  ./LowFactor to go to a subfolder from the current folder

29/ cd .. go back to the parent folder.

30/ Check Memory Used

sacct -o reqmem,maxrss,averss,elapsed,alloccpus -j 3413279


Go to scratch: cd /mnt/scratch/lethien1

6/ scancel 2062746

7/ Cancel a sequence of jobs with id from 1 to 10: 
scancel {1..10}
[] (cancel jobs)
scancel -u <username>
CTRL C for terminating R

7/ Rscript HpccTried
.R 100 100 4(Check code)

