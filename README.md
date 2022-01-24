<div align = "centre">

# RPC
	
</div> 

### Installation

```bash
sudo apt-get install rpcbind
```

### After Successful Installation 

```bash
rpcinfo
```

![image](https://user-images.githubusercontent.com/52845731/150816460-c695270b-b538-4822-a3b6-2eb05fcbbfa0.png)


### Creating Calculator Program

```c
struct numbers
{
	int a;
	int b;
	int c;
};

program CALC_PROGRAM
{
	version CALC_VERS
	{
		int calc(numbers) = 1;
	} = 1;	

} = 0x23451111;
```

### Compile 

```bash
rpcgen -a -C calc.x
```

- Using make command, create all other files that are necessary as per the RPC Structure. 

```bash
make -f Makefile.calc
```

- Make required modifications to Client and Server files that are created. 

### Run Server

```bash
sudo ./calc.server
```

## Run Client 

```bash
sudo ./calc.client localhost <Arguments>
```
