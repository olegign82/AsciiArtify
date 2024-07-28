1. Create a file with the name kubectl-kubeplugin and copy the contents of the scripts/kubeplugin file to it

2. Make the file executable:
``sudo chmod +x ./kubectl-kubeplugin``

3. Move this file to your PATH:
``sudo mv ./kubectl-kubeplugin /usr/local/bin``

4. Invoke your plugin as kubectl command:
``kubectl kubeplugin kube-system nodes``
