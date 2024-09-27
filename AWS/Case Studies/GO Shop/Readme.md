**Case Study Company Name: Gunda Online Shop (GO Shop)**



<h1>Create and Deploy a Business via AWS Using a LAMP Stack</h1>

<table>
  <thead>
    <tr>
      <th>Resource</th>
      <th>Cloud Resource</th>
      <th>Comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Web Application Server</td>
      <td>EC2 (with auto scaling LB)</td>
      <td>Managed service for easy deployment and scaling of applications. <strong>Instance type: m5.large</strong></td>
    </tr>
    <tr>
      <td>Database Server</td>
      <td>Amazon RDS (Relational Database Management)</td>
      <td>Managed relational database with Multi-AZ for high availability. <br><code>VPC: 192.167.0.0/16</code>, Running MySQL Community</td>
    </tr>
    <tr>
      <td>File Server</td>
      <td>Amazon S3 Standard</td>
      <td>Store/retrieve files <br> High durability <br> Install EC2 instance onto S3 bucket</td>
    </tr>
    <tr>
      <td>Software Dev Environment</td>
      <td>AWS Cloud9</td>
      <td>Centralized, web-based software development.</td>
    </tr>
    <tr>
      <td>Identity and Access Management</td>
      <td>AWS IAM</td>
      <td>Define permissions and access. Enable MFA for security.</td>
    </tr>
    <tr>
      <td>VPC Configuration</td>
      <td>AWS VPC</td>
      <td>VPC: <code>192.167.0.0/16</code>, Subnets: <code>192.168.1.0/24</code> and <code>192.168.0.0/24</code></td>
    </tr>
  </tbody>
</table>






GO Shop is a small online store which sells various items such as household goods, computer spare parts, cables, garden tools etc. The company uses an in-house developed web application software running on its own servers. The company has been operating with this system for a long time and the application has been fine tuned for their purpose. With the rapid increase in the business transactions during and the pandemic, the old hardware platform is pushed to limits. This has given rise to issues resulting in increased system administration tasks for in-house IT staff and the Senior system administrator is requesting more staff from the management to manage the systems.
After having several discussions with the Management, GO Shop decides to explore the possibility of implementing a cloud-based system so that the company does not need to maintain the in-house IT infrastructure. Current Configuration IT Systems: ● Domain Controller ● Web Application Server ● Database Server ● File Server Business Needs: ● Reliable servers with reduced hardware maintenance cost ● Maintain current level of System Administration staff ● Reduced utility costs for IT infrastructure ● Use the existing well-tuned online transaction system and the database ● Secure File storage ● High availability servers ● Access GO Shop application from anywhere in the world with minimum response time.
