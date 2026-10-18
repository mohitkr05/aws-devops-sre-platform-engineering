# Backups & Snapshots

## Day 11

- [ ] Backup best practices
- [ ] What is a snapshot?
- [ ] How to save a snapshot in Lightsail
- [ ] Scheduling a snapshot.
- [ ] Restoring from a snapshot


## What are the best practices for backups


- Regular backups: Regular backups ensure that you have an up-to-date copy of your data in case of a disaster. The frequency of backups depends on the amount of data you have and how critical it is.
- Multiple backups: It’s a good idea to keep multiple backups, preferably in different locations. This helps protect against data loss due to natural disasters or other catastrophic events.
- Automation: Automating the backup process ensures that backups are done consistently and on time. This also helps reduce the risk of human error.
- Offsite storage: Storing backups offsite is important in case of a disaster or theft. Cloud storage can be an easy and secure option for offsite storage.
- Encryption: Encrypting backups adds an extra layer of security to your data. This prevents unauthorized access to sensitive data in case of theft or data breach.
- Testing: Regularly test backups to ensure that they are working properly and can be restored in case of a disaster.
- Retention: Determine how long backups should be kept and when they should be deleted. This helps prevent the accumulation of unnecessary data and reduces storage costs.
- Monitoring: Regularly monitor backups to ensure that they are running smoothly and that there are no errors or issues.

## What is a Snapshot

- A snapshot is a point-in-time copy of a particular resource, such as a disk, volume, or instance in a cloud computing environment.
- It captures the current state of the resource, including all the data and settings that have been configured up to that point.
- Snapshots are useful for creating backups, restoring data in case of data loss, and migrating resources to different environments.
- They are a way of creating a recovery point for your resources, allowing you to quickly restore them in case of unexpected failure or data corruption.
- In some cloud computing environments, snapshots are automatically created on a regular basis, providing an additional layer of data protection.
- Snapshots can be stored in different locations, such as within the same region or across multiple regions, depending on the specific cloud provider's capabilities.
- Some cloud providers charge for storing snapshots, while others may offer free storage up to a certain amount.


## How to take a snapshot in Lightsail

- Log in to your Lightsail account and navigate to the Lightsail home page.
- Select the instance you want to create a snapshot for.
- Click on the "Snapshots" tab.
- Click the "Create snapshot" button.
- In the "Create snapshot" dialog box, enter a name and description for the snapshot.
- Click the "Create snapshot" button.

## How to restore from a snapshot in Lightsail

- Log in to your Lightsail console.
- Click on the "Snapshots" tab in the left-hand navigation menu.
- Select the snapshot you want to restore from, and click the "Create instance" button.
- In the "Create an instance from a snapshot" page, enter a name for your new instance and select the Lightsail region where you want to create it.
- Choose the instance plan and bundle size you want to use for the new instance, and click the "Create instance" button at the bottom of the page.
- Lightsail will start creating the new instance from the snapshot. Once it's done, you can connect to it and start using it just like any other Lightsail instance.

