<h1 class="code-line" data-line-start=0 data-line-end=1 ><a id="Ansible_role_for_building_a_lamp_stack_with_wordpress_site_on_CentOS7_and_Amazon_Linux2_0"></a>Ansible role for building a lamp stack with wordpress site on CentOS7 and Amazon Linux2.</h1>
<p class="has-line-data" data-line-start="2" data-line-end="3">This is a Ansible role to deploy a LAMP Stack infrastructure on centos7/amazon-linux2 hosts.</p>
<ul>
<li class="has-line-data" data-line-start="4" data-line-end="6">Playbooks for complex tasks can become lengthy and therefore difficult to read and understand. The solution to this problem is Ansible roles. A role directory structure contains directories: defaults, vars, tasks, files, templates, meta, handlers. Each directory must contain a main.yml file which contains relevant content.</li>
</ul>
<p class="has-line-data" data-line-start="6" data-line-end="7">Here is the role I have created for this project,</p>
<pre><code class="has-line-data" data-line-start="8" data-line-end="34" class="language-sh">├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── inventory.txt
├── key.pem
├── lamp-wordpress.yml
├── meta
│   └── main.yml
├── README.md
├── tasks
│   ├── amazon.yml
│   ├── centos.yml
│   ├── main.yml
│   └── wordpress.yml
├── templates
│   ├── httpd.conf.temp
│   ├── virtualhost.conf.temp
│   └── wp-config.php.temp
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
</code></pre>
<h4 class="code-line" data-line-start=35 data-line-end=36 ><a id="STACK_35"></a>STACK</h4>
<ul>
<li class="has-line-data" data-line-start="36" data-line-end="37">apache</li>
<li class="has-line-data" data-line-start="37" data-line-end="38">php7.4</li>
<li class="has-line-data" data-line-start="38" data-line-end="39">mariadb-server</li>
</ul>
<h4 class="code-line" data-line-start=39 data-line-end=40 ><a id="Prerequisites_39"></a>Prerequisites</h4>
<p class="has-line-data" data-line-start="40" data-line-end="41">You must have the latest ansible version installed.</p>
<h4 class="code-line" data-line-start=41 data-line-end=42 ><a id="Hosts_41"></a>Hosts</h4>
<ul>
<li class="has-line-data" data-line-start="42" data-line-end="43">Add hosts in an inventory file under your working directory.</li>
</ul>
<h4 class="code-line" data-line-start=43 data-line-end=44 ><a id="Apache__Database_configuration_43"></a>Apache &amp; Database configuration</h4>
<ul>
<li class="has-line-data" data-line-start="44" data-line-end="45">I have included the configuration informations for both apache and mariadb in the vars section. Please modify as per your requirement.</li>
</ul>
<h4 class="code-line" data-line-start=45 data-line-end=46 ><a id="Setup_45"></a>Setup</h4>
<p class="has-line-data" data-line-start="46" data-line-end="47">Run the below command to check if the playbook have any syntax error,</p>
<pre><code class="has-line-data" data-line-start="49" data-line-end="51" class="language-sh">ansible-playbook -i inventory.txt lamp-wordpress.yml --syntax-check
</code></pre>
<p class="has-line-data" data-line-start="51" data-line-end="52">then,</p>
<pre><code class="has-line-data" data-line-start="53" data-line-end="55" class="language-sh">ansible-playbook -i inventory.txt lamp-wordpress.yml
</code></pre>
<p class="has-line-data" data-line-start="56" data-line-end="57"><em>Thank you.</em></p>
