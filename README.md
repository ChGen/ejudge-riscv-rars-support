# ejudge-riscv-rars-support

RARS RISC-V CPU Simulator support for EJudge contest management system
1. Preparations:
    1. Download RARS Simulator .jar file and install java runtime
    2. Create rars symlink (rars-simulator) for EJudge, e.g.: `sudo ln -s  '/home/ejudge/rars_1.5.jar' /usr/local/bin/rars-simulator`
2. EJudge integration:
    * Put both `*.in` files in `$EJUDGE_PREFIX/libexec/ejudge/lang` in (e.g. /home/ejudge/inst-ejudge/libexec/ejudge/lang/in) and run `ejudge-setup`
    * Or put both `*.in` files in `/home/ejudge/compile/scripts/in` and run `ejudge-configure-compilers`. 
3. Update EJudge limits (because RARS is java-based simulator), e.g. for `/home/judges/000001/conf/serve.cfg` set:
```
[problem]
max_vm_size = 64G
max_stack_size = 64G
max_file_size = 64G
time_limit = 10
```
4. References:
    * RARS RISC-V CPU Simulator: https://github.com/TheThirdOne/rars
    * EJudge contest management system: https://github.com/blackav/ejudge
    * EJudge wiki: https://ejudge.ru/wiki/index.php/%D0%A1%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0_ejudge
5. Some known issues:
    * RARS executes asm files without extentions without user input O_o. Maybe they are treated as binary/compiled files?
    * No built-in way in RARS to disable 1st (copyright) & last (exit type) output lines to stdio
    * RARS syscall for reading int's - no EOF handling
 
