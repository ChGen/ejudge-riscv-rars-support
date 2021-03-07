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
