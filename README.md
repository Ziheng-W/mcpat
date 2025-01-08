### McPAT 1.3 Modified.

What's modified?

1. Initialization phase and computation phase are decoupled.
   
   - Initialization of a processor is done directly in the instantiation of it.
   
   - Area computing is left unchanged in initialization (a chip is just a chip, not a transformer)
   
   - Power computing is picked out into a new function, `compute`.

2. Consecutive simulation is enabled.
   
   - Modified McPAT can initialize for just once and keep computing new power stats upon new XML files.

How to use?

- The command of original McPAT is still supported.
  
  ```shell
  mcpat -infile <name> -print_level <0~5> -opt_for_clk <0/1>
  ```

- To enable consecutive simulation, use command `-trace`.
  
  So the command becomes:
  
  ```shell
  mcpat -trace -infile <name> -print_level <0~5> -opt_for_clk <0/1>
  ```
  
  After simulating upon the initial XML file, McPAT waits for you to input a new filename. This continues until you input "exit" and ends the program.
  
  If you input "repeat", McPAT computes upon the last XML interface.
























