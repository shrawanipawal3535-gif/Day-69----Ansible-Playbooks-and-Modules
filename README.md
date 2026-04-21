# Day-69----Ansible-Playbooks-and-Modules

## Task
Ad-hoc commands are useful for quick checks, but real automation lives in playbooks. A playbook is a YAML file that describes the desired state of your servers -- which packages to install, which services to run, which files to place where. You write it once, run it a hundred times, and get the same result every time.

Today you write your first playbooks and learn the modules that you will use on every project.

## Expected Output

- Multiple playbooks that install packages, manage services, and configure files
- A clear understanding of plays, tasks, modules, and handlers
- A markdown file: day-69-playbooks.md
  
# Challenge Tasks

# Task 1: Your First Playbook

Create install-nginx.yml:

<img width="668" height="415" alt="image" src="https://github.com/user-attachments/assets/73ddfc19-83cf-4748-bb1e-6e419b829463" />


Run it:
<img width="392" height="47" alt="image" src="https://github.com/user-attachments/assets/be3e18c1-583a-40bb-b5c1-a6936d4677e9" />

<img width="972" height="554" alt="Image" src="https://github.com/user-attachments/assets/34d6a4d1-da48-48a4-a60b-792ce9970139" />
<img width="1019" height="403" alt="Image" src="https://github.com/user-attachments/assets/0f12f676-ce4e-41f0-8234-1d2a8a629422" /> 
<img width="849" height="390" alt="Image" src="https://github.com/user-attachments/assets/f2544d81-0286-40db-af2f-58704ee0d815" /> 

## Task 2: Understand the Playbook Structure

Open your playbook and annotate each part in your notes:

<img width="609" height="208" alt="image" src="https://github.com/user-attachments/assets/6903e125-01a9-4a6f-a9d4-a9ebd36814fa" />

<img width="1065" height="740" alt="Image" src="https://github.com/user-attachments/assets/d45a5363-edb6-4064-86fe-ca38c8d22149" /> 
<img width="1139" height="309" alt="Image" src="https://github.com/user-attachments/assets/b97aacab-2dc8-403c-a5f0-60165d4bbbfe" /> 



1. What is the difference between a play and a task?
- Play → Defines which hosts to target and groups multiple tasks
- Task → A single action/step performed on hosts

2. Can you have multiple plays in one playbook?
- YES ✔️
- One playbook can contain multiple plays
- Each play can target different host groups

  
3. What does become: true do at the play level vs the task level?

 Play level:
 - Applies to all tasks in that play
🔹 Task level:
 - Applies to only that specific task


4. What happens if a task fails -- do remaining tasks still run?
  - Execution stops immediately
  - Remaining tasks →  NOT executed

# Task 3: Learn the Essential Modules

Practice each of these modules by writing a playbook called essential-modules.yml with multiple tasks:

1. yum/apt -- Install and remove packages:

<img width="402" height="181" alt="image" src="https://github.com/user-attachments/assets/b3fc4d48-df4b-490e-a94f-20dcc6e82d87" />

2. service -- Manage services:

<img width="366" height="122" alt="image" src="https://github.com/user-attachments/assets/bb056f97-2144-4e2b-90e8-dfe2caf27129" />

3. copy -- Copy files from control node to managed nodes:

<img width="420" height="173" alt="image" src="https://github.com/user-attachments/assets/d74f0943-0c2b-49e5-bdfd-c338bb69e5e1" />

4. file -- Create directories and manage permissions:

<img width="409" height="159" alt="image" src="https://github.com/user-attachments/assets/608abe0b-24e8-4ed0-91d9-d6a7d45f7124" />

5. command -- Run a command (no shell features):

 <img width="390" height="161" alt="image" src="https://github.com/user-attachments/assets/70b44ca6-ec58-449c-8500-dfa68ec4e36d" />

6. shell -- Run a command with shell features (pipes, redirects):

 <img width="532" height="164" alt="image" src="https://github.com/user-attachments/assets/91e8654b-4c39-44a4-a8a9-59b6d2acca3e" />

7. lineinfile -- Add or modify a single line in a file:

<img width="378" height="114" alt="image" src="https://github.com/user-attachments/assets/b25e087f-d81e-40d6-ab3b-db53ae788183" />

<img width="941" height="515" alt="Image" src="https://github.com/user-attachments/assets/447f59e5-4b29-4d50-9723-157c37f7af52" /> 

<img width="936" height="456" alt="Image" src="https://github.com/user-attachments/assets/770aee11-8a00-4a7d-b938-2b89701ab476" /> 
<img width="521" height="213" alt="Image" src="https://github.com/user-attachments/assets/ce220e41-7f8d-40e7-9f02-8527487b2395" /> 

# Task 4: Handlers -- Restart Services Only When Needed

Handlers are tasks that run only when triggered by a notify. This avoids unnecessary service restarts.

Create nginx-config.yml:

<img width="759" height="714" alt="image" src="https://github.com/user-attachments/assets/a72aed1f-0ea3-42ee-b49a-df60c87d34e5" />

# Task 5: Dry Run, Diff, and Verbosity

Before running playbooks on production, always preview changes first.

1. Dry run (check mode) -- shows what would change without changing anything:

<img width="374" height="43" alt="image" src="https://github.com/user-attachments/assets/2a783e52-f37a-49b0-8486-05ba26c7a950" />

<img width="1169" height="398" alt="Image" src="https://github.com/user-attachments/assets/68f9eba0-b3d6-4f47-b00c-fcd67c73a1b4" />

<img width="1093" height="384" alt="Image" src="https://github.com/user-attachments/assets/9071bcb5-7fd0-4100-a6a4-95f9fcd6114f" /> 

2. Diff mode -- shows the actual file differences:

<img width="472" height="48" alt="image" src="https://github.com/user-attachments/assets/51d40a95-7155-436e-a3c6-4dc5fd31fe0f" />

<img width="1184" height="461" alt="Image" src="https://github.com/user-attachments/assets/ffe83567-7362-480f-a617-e343d9660c14" />


3. Verbosity -- increase output detail for debugging:

<img width="613" height="76" alt="image" src="https://github.com/user-attachments/assets/70b0f7d8-edc7-486e-a13b-ebab9d0ca246" />

<img width="937" height="538" alt="Image" src="https://github.com/user-attachments/assets/613d3fa6-57f4-4201-bd55-2c3783e42857" />
<img width="936" height="974" alt="Image" src="https://github.com/user-attachments/assets/baa09e46-1a13-470e-8944-a6f7292d09e4" /> 
<img width="936" height="972" alt="Image" src="https://github.com/user-attachments/assets/e46b5c6d-2bfd-4a09-b1d0-c29fff84777c" /> 

4. Limit to specific hosts:

<img width="452" height="41" alt="image" src="https://github.com/user-attachments/assets/4f64c937-ee04-4ddd-8dec-f413017c0973" />

<img width="935" height="389" alt="Image" src="https://github.com/user-attachments/assets/1d47fa17-6258-453f-a43d-07810c37f4c7" />



5. List what would be affected without running:

<img width="412" height="65" alt="image" src="https://github.com/user-attachments/assets/0d59498a-fb89-4751-a8ae-e5843de43838" />

<img width="887" height="351" alt="Image" src="https://github.com/user-attachments/assets/d2ecffeb-8da0-4d2c-ab02-84a5d86ff89d" /> 


# Task 6: Multiple Plays in One Playbook

Write multi-play.yml with separate plays for each server group:

<img width="551" height="741" alt="image" src="https://github.com/user-attachments/assets/ee302a56-0541-426e-949a-0d9501aafd8f" />

Run it:

<img width="249" height="23" alt="image" src="https://github.com/user-attachments/assets/83ff8957-72ab-4090-b979-4fc94cecec5b" />

<img width="969" height="766" alt="Image" src="https://github.com/user-attachments/assets/13b9abce-cf73-4d5d-9bfa-d506229c9dce" />


