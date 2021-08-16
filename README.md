## Artifact for the FMCAD'21 paper:
   
#   *Towards an Automatic Proof of Lamport's Paxos*
--------------------------------------------------------------------------
includes:
- all experimental data and logs
- all detailed results tables
- all evaluation scripts
- IC3PO source code for replicating the runs
- source code for each tool (all openly available) for replicating the runs

#### Resource requirements:
- 6 cores (to run each tool in parallel)
- 32 GB RAM should be enough
- roughly 4-6 days for complete evaluation (on a ~3GHz Intel CPU)

#### Description
The artifact evaluates the tool IC3PO presented in the paper for verifying 
Paxos, and compares it against other state-of-the-art verifiers: 
SWISS, fol-ic3, DistAI, I4, and UPDR.

Check the License.txt in the artifact for license information.

Note-
If the experiments are too resource intensive for your machine,
change the line timeMax="18000" to  timeMax="3600" in the following files:
   - exp/ic3po/ic3po.sh
   - exp/i4/i4.sh
   - exp/mypyv/updr.sh
   - exp/mypyv/folic3.sh
   - exp/swiss/swiss.sh
   - exp/distai/distai.sh
   
All compiled results are available in exp/results/* folder.
All detailed logs are available in exp/<tool>/output*/* folder.
   
Please contact the authors for any  technical help or clarification relating to 
reproducing the results or analyzing the experimental logs and scripts.
   
#### How to run
Make sure the artifact is in the /home/username/ directory.
This means, this file should be present at /home/username/artifact/README.txt

Installation:
  -- install solvers:
	z3       - https://github.com/Z3Prover/z3/releases/tag/z3-4.8.10
	yices2 - https://github.com/SRI-CSL/yices2
  -- install python2 bindings of solvers:
	z3       - https://github.com/Z3Prover/z3/releases/tag/z3-4.8.10
	yices2 - https://github.com/SRI-CSL/yices2_python_bindings
  -- install additional requirements:
	ivy, pysmt -- run ./build.sh in exp/ic3po/ic3po-rb
  -- install any required packages for other tools: SWISS, fol-ic3, I4, updr, DistAI


  -- Add the following to your /home/username/.bashrc
     export EXPATH=/home/username/artifact/exp
     export IC3POPATH=$EXPATH/ic3po/ic3po-rb
     export PYSMT_PATH=$IC3POPATH/pysmt
     export PYTHONPATH=$PYSMT_PATH:$PYTHONPATH
  
  source /home/username/.bashrc
  echo $EXPATH	-- Make sure this returns /home/username/artifact/exp
  cd ..
  pwd			-- Make sure this returns /home/username/artifact
  
  -- enter the EXPATH directory
     cd $EXPATH

For complete assessment, run:
  KICK=0 ./run_all.sh
  
All compiled results are produced in exp/results/* folder.
All detailed logs are produced in exp/<tool>/output*/* folder.


##### IMPORTANT NOTE ON AVAILABILITY
The IC3PO tool is maintained on a public github repository-- 
	https://github.com/aman-goel/ic3po.

We would be glad to hear from you and help you in the case you are having a difficulty
 in using IC3PO. Please report bugs and share your usage experience 
 via email  [(amangoel@umich.edu)](amangoel@umich.edu) or on github [(https://github.com/aman-goel/ic3po)](https://github.com/aman-goel/ic3po).
