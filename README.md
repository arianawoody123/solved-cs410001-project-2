Download Link: https://assignmentchef.com/product/solved-cs410001-project-2
<br>



<strong> </strong>

<ol>

 <li>Project Objective

  <ol>

   <li>Implement a pipelined, functional processor simulator for the reduced MIPS R3000 ISA, following the specification “<em>Datasheet for the Reduced MIPS R3000 ISA</em>” in <em>Appendix A</em></li>

   <li>Design your own test case to validate your implementation, particularly on hazards handling.</li>

  </ol></li>

</ol>




<ol start="2">

 <li>Project Description

  <ol>

   <li>Pipeline Description</li>

  </ol></li>

</ol>




<ol>

 <li>5 stages in pipeline: instruction fetch (IF), instruction decode (ID), ALU execution (EX), data memory access (DM) and write back (WB).</li>

 <li><strong>Conditional branches and unconditional branches are determined during the ID stage. </strong></li>

</ol>

<ul>

 <li><strong>Load/store computes the address to be accessed in D memory during the EX stage, and accesses data memory during the DM stage. </strong></li>

</ul>

<ol>

 <li>Arithmetic/bitwise shift/logical operations are done during the EX stage.</li>

 <li>There are two forwarding paths: EX/DM to ID, EX/DM to EX.</li>

 <li>All <strong>write back</strong> executions targeting to $0~$31 <strong>are done during the first half of the cycle</strong> in the WB stage. vii. All <strong>reads to registers are done during the second half of the cycle</strong> in the ID stage.</li>

</ol>

<ul>

 <li>PC is updated in each cycle <strong>after</strong> executing all instructions in each pipeline stage.</li>

</ul>

<ol>

 <li>If inserting “NOPs” is needed to resolve hazards, use <em>sll $0, $0, 0</em>, i.e. the bit stream 0x00000000<sub>h</sub>. <strong>In your implementation, you should decode </strong>the instruction bit stream 0x00000000<sub>h</sub><strong> as NOP</strong>.</li>

 <li>Other Constraints

  <ol>

   <li>The pipeline is <strong>initialized </strong>with<strong> NOPs in all stages</strong>.</li>

   <li>The simulation of the pipelined processor <strong>terminates </strong>after the<strong> five “halt” </strong>instructions arriving<strong> all the stage.</strong></li>

  </ol></li>

</ol>

<ul>

 <li><strong>Register 0 </strong>is a <strong>hard-wired 0</strong>; any attempt to write to register 0 takes no effect. iv.          The instruction memory is of 1K bytes size, the data memory of 1K bytes size.</li>

</ul>

<ol>

 <li>The executable should be named <strong>pipeline</strong>.</li>

 <li><strong>To avoid re-execution of some stages, the order of simulating the pipeline is WB </strong></li>

</ol>

→ <strong>DM </strong>→<strong> EX </strong>→<strong> ID </strong>→<strong> IF.  </strong>

<strong> </strong>

<ol start="3">

 <li>Input Test Case File and Format</li>

</ol>

Same as Project 1. Please refer to the specification of Project 1 and <em>Appendix B</em>, “<em>Sample Input</em>.”

<ul>

 <li><strong>Note:</strong> Your test case should cover at least one control hazard and one data hazard resolved by inserting NOPs, and one data hazard cleared by forwarding.</li>

</ul>




<ol start="4">

 <li>Output Requirement</li>

</ol>

<ul>

 <li>    For each test case, generate the following two output files:

  <ol>

   <li><strong>rpt :</strong> Record all the register values at each cycle.</li>

   <li><strong>rpt : </strong>Record any error messages.</li>

  </ol></li>

 <li>Place the output files at the same directory where your executable file resides.</li>

 <li>For details, please refer to <em>Appendix C-2</em>, “<em>Sample Output for Project 2</em>.” and <em>Appendix D</em>, <em>“Error Detection Sample</em>”.</li>

</ul>




<ol start="5">

 <li>The 2-submission Process</li>

</ol>

Same as Project 1, but with the following modification: The cloned repository from GitHub should be named studentID_02/. At submission, compress the folder studentID_02 as studentID_02.tar.gz, and upload studentID_02.tar.gz and studentID_report.pdf to the iLMS system.




<ol start="6">

 <li>Grading Policy</li>

</ol>

Same as project 1.

<strong>Note</strong>: Demo parts will focus on:

<ol>

 <li>Structure of Pipeline</li>

 <li>Design of Pipeline</li>

 <li>Hazard Concepts</li>

 <li>Forwarding Path’ s Effect</li>

</ol>

<strong> </strong>


