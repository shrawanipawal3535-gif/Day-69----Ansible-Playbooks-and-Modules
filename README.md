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

## Task 2: Understand the Playbook Structure

Open your playbook and annotate each part in your notes:

<img width="609" height="208" alt="image" src="https://github.com/user-attachments/assets/6903e125-01a9-4a6f-a9d4-a9ebd36814fa" />

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

# Task 4: Handlers -- Restart Services Only When Needed

Handlers are tasks that run only when triggered by a notify. This avoids unnecessary service restarts.

Create nginx-config.yml:

<img width="759" height="714" alt="image" src="https://github.com/user-attachments/assets/a72aed1f-0ea3-42ee-b49a-df60c87d34e5" />

# Task 5: Dry Run, Diff, and Verbosity

Before running playbooks on production, always preview changes first.

1. Dry run (check mode) -- shows what would change without changing anything:

<img width="374" height="43" alt="image" src="https://github.com/user-attachments/assets/2a783e52-f37a-49b0-8486-05ba26c7a950" />

2. Diff mode -- shows the actual file differences:

<img width="472" height="48" alt="image" src="https://github.com/user-attachments/assets/51d40a95-7155-436e-a3c6-4dc5fd31fe0f" />

3. Verbosity -- increase output detail for debugging:

<img width="613" height="76" alt="image" src="https://github.com/user-attachments/assets/70b0f7d8-edc7-486e-a13b-ebab9d0ca246" />

4. Limit to specific hosts:

<img width="452" height="41" alt="image" src="https://github.com/user-attachments/assets/4f64c937-ee04-4ddd-8dec-f413017c0973" />

5. List what would be affected without running:

<img width="412" height="65" alt="image" src="https://github.com/user-attachments/assets/0d59498a-fb89-4751-a8ae-e5843de43838" />

# Task 6: Multiple Plays in One Playbook

Write multi-play.yml with separate plays for each server group:

<img width="551" height="741" alt="image" src="https://github.com/user-attachments/assets/ee302a56-0541-426e-949a-0d9501aafd8f" />

Run it:

<img width="249" height="23" alt="image" src="https://github.com/user-attachments/assets/83ff8957-72ab-4090-b979-4fc94cecec5b" />














   


