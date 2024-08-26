# Linux-for-File-Permission-Management
<h2>Scenario</h2>
<p>
  You are a security professional at a large organization, primarily working with their research team. One of your key responsibilities is to ensure that team members have the appropriate permissions, which is crucial for maintaining system security.</p>

<p>Your task involves reviewing the current file system permissions. You need to verify if the permissions align with the required authorizations. If discrepancies are found, you will adjust the permissions to grant access to authorized users and revoke access from unauthorized ones.</p>

<h3>Solution</h3>
<b>Step 1: <br>Checking file and directory details</b>
<p>
  Important commands used to check file and directory details are:
  <ul>
    <li><pre>ls command - Displays all files and sub-directories within a directory.</pre></li>
    <li><pre>ls -l command - Lists the contents of a directory along with their permissions.</pre></li>
    <li><pre>ls -a command - Shows hidden files in the directory.</pre></li>
  </ul>
  By combining commands (2) and (3) as ls -al, you can list the contents and permissions of both visible and hidden files within the directory.
 <img width="738" alt="bukolasehinde-Linux1" src="https://github.com/user-attachments/assets/3d835a44-39a8-4a92-ac99-84b955750cc4">

</p>

<b>Step 2: <br>Description of the permissions string above</b>
<p>
  The 10-character string (`rwxrwxrwx`) represents the read, write, and execute permissions for users, groups, and others in the filesystem. For directories(d), the permissions string appears as: <pre>drwxrwxrwx</pre> while for regular files(-) it is represented as: <pre>-rwxrwxrwx</pre>
</p>

<b>Step 3: <br>Changing file permissions</b>
<p>
  The organization prohibits granting write access to files for others. As a system administrator adhering to the principle of least privilege, I reviewed files with incorrect permissions and adjusted them as necessary.<br>
<img width="805" alt="bukolasehinde-Linux2" src="https://github.com/user-attachments/assets/9d5c0ced-c9ed-4657-b24d-a2d62cfa845e">

<u>
  <li>The file "project_k.txt" has write permissions for others, which violates the organization's policy. To remove the write permission, I executed the following command:
    <pre>chmod o-w project_k.txt</pre></li>
  <li>Additionally, the file "project_m.txt" is a restricted file and should not be readable or writable by the group. To ensure this, I entered the following command to remove the group's read permissions from the file.
    <pre>chmod g-r project_m.txt</pre></li>
  </u>
</p>

<b>Step 4: <br>Changing file permissions on a hidden file</b>
<p>
  Since the research team has archived ".project_x.txt," it is a hidden file and should not have write permissions for anyone. However, both the user and group should still be able to read the file. br>As the system administrator, I used the following command to assign the appropriate permissions.
  <pre>chmod u-w,g-w,g+r .project_x.txt</pre>
<img width="766" alt="bukolasehinde-Linux3" src="https://github.com/user-attachments/assets/3f316663-e8a8-45b9-a852-57311e6cfdc3">
  <br>This will limit unauthorized access and enhance the system's security.
</p>

<b>Step 5: <br>Changing directory permissions</b>
<p>
  <img width="735" alt="bukolasehinde-Linux4" src="https://github.com/user-attachments/assets/f1c6d251-1181-4109-a02f-087cc3fd2e56">

  <br>The files and directories within the projects directory belong to the user "researcher2," meaning only this user should have access to the drafts directory and its contents. br>As a Linux system administrator, I used the following command to adjust the permissions accordingly:
  <pre>chmod g-x drafts</pre>
  This command removes execute permission for the group, ensuring that only the "researcher2" user has access to the drafts directory and its contents.
</p>

<b>Summary:</b>
<p>
 As a Linux system administrator and cybersecurity professional, I successfully reviewed the existing permissions on the organization's file system, adjusted them to authorize the appropriate users, and removed all unauthorized access. This application of the principle of least privilege has further enhanced the organization's security system and posture.
</p>
