**Case Study Company Name: Gunda Online Shop (GO Shop)**



<h1 style="text-align:center; color:#1E3A8A;">Create and Deploy a Business via AWS Using a LAMP Stack</h1>

<table style="width:100%; border:2px solid #1E3A8A; border-collapse: collapse; font-family: Arial, sans-serif;">
  <thead style="background-color:#1E3A8A; color:white; text-align:left;">
    <tr>
      <th style="padding:10px; border:1px solid #1E3A8A;">Resource</th>
      <th style="padding:10px; border:1px solid #1E3A8A;">Cloud Resource</th>
      <th style="padding:10px; border:1px solid #1E3A8A;">Comments</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding:10px; border:1px solid #1E3A8A;">Web Application Server</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">EC2 (with auto scaling LB)</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Managed service for easy deployment and scaling of applications. <strong>Instance type: m5.large</strong></td>
    </tr>
    <tr style="background-color:#E0E7FF;">
      <td style="padding:10px; border:1px solid #1E3A8A;">Database Server</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Amazon RDS (Relational Database Management)</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Managed relational database with Multi-AZ for high availability. <br><code>VPC: 192.167.0.0/16</code>, Running MySQL Community</td>
    </tr>
    <tr>
      <td style="padding:10px; border:1px solid #1E3A8A;">File Server</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Amazon S3 Standard</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Store/retrieve files <br> High durability <br> Install EC2 instance onto S3 bucket</td>
    </tr>
    <tr style="background-color:#E0E7FF;">
      <td style="padding:10px; border:1px solid #1E3A8A;">Software Dev Environment</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">AWS Cloud9</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Centralized, web-based software development.</td>
    </tr>
    <tr>
      <td style="padding:10px; border:1px solid #1E3A8A;">Identity and Access Management</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">AWS IAM</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">Define permissions and access. Enable MFA for security.</td>
    </tr>
    <tr style="background-color:#E0E7FF;">
      <td style="padding:10px; border:1px solid #1E3A8A;">VPC Configuration</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">AWS VPC</td>
      <td style="padding:10px; border:1px solid #1E3A8A;">VPC: <code>192.167.0.0/16</code>, Subnets: <code>192.168.1.0/24</code> and <code>192.168.0.0/24</code></td>
    </tr>
  </tbody>
</table>





GO Shop is a small online store which sells various items such as household goods, computer spare parts, cables, garden tools etc. The company uses an in-house developed web application software running on its own servers. The company has been operating with this system for a long time and the application has been fine tuned for their purpose. With the rapid increase in the business transactions during and the pandemic, the old hardware platform is pushed to limits. This has given rise to issues resulting in increased system administration tasks for in-house IT staff and the Senior system administrator is requesting more staff from the management to manage the systems.
After having several discussions with the Management, GO Shop decides to explore the possibility of implementing a cloud-based system so that the company does not need to maintain the in-house IT infrastructure. Current Configuration IT Systems: ● Domain Controller ● Web Application Server ● Database Server ● File Server Business Needs: ● Reliable servers with reduced hardware maintenance cost ● Maintain current level of System Administration staff ● Reduced utility costs for IT infrastructure ● Use the existing well-tuned online transaction system and the database ● Secure File storage ● High availability servers ● Access GO Shop application from anywhere in the world with minimum response time.
