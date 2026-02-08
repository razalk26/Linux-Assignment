# 1. Setup and Directory Creation
mkdir ev4
cd ev4
mkdir 42
cd 42

# 2. Navigation Commands
cd -
cd -
cd .
cd ..
cd ~
cd /
ls -l
cd media
cd
pwd
cd media        # This will give error (No such file)
cd /media
ls -l
cd ~/ev4/42

# 3. File and Directory Management
mkdir emptydummy
mkdir dummy
cd dummy
touch file1
touch file2
ls -l
rm -i file2
cd ..
rm emptydummy          # Will fail (Is a directory)
rmdir emptydummy
rmdir dummy            # Will fail (Directory not empty)
rm -r dummy

# 4. File Content and Redirection (I/O)
cat > file1.txt
# Type: My first line
# Press Ctrl + D

cat > file2.txt
# Type: Hello Second line
# Press Ctrl + D

cat > file3.txt
# Type: Hello line
# Press Ctrl + D

cat file1.txt file2.txt > file_combined.txt
cat file_combined.txt
cat file3.txt >> file_combined.txt
cat file_combined.txt
grep -i hello file*
cp file1.txt ~/ev4
mv file_combined.txt combined

# 5. Permissions (chmod)
chmod u+x file.sh
chmod g-w file.txt
chmod a+r file.txt
chmod u=rwx,g=rx,o=r myfile
chmod 754 file.txt
chmod 600 file.txt
chmod u+x combined
chmod g-r combined
chmod 777 combined

# 6. User Management (sudo)
sudo useradd alice
sudo passwd alice
sudo userdel alice

# 7. Communication
write alice
mesg y
mesg n
