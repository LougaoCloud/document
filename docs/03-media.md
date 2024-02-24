
# Media (Optional)

When deploying WordPress in a Serverless manner, you have the option to separate media files and WordPress files, storing images, videos, and other files separately. The separation offers the following benefits:

1. **Performance Optimization:** Storing media files such as images and videos on a separate server or Content Delivery Network (CDN) can enhance website performance. CDNs enable the distribution of these files to servers worldwide, thereby accelerating file loading speeds.

2. **Backup and Restore:** Separating media files and the wp-content directory simplifies the backup and restore process. You can more frequently back up core WordPress files and the database without the need to backup a large volume of media files, improving backup efficiency.

3. **Reducing Serverless Function Traffic Costs:** As Alibaba Cloud's Function Compute charges for outbound traffic, separating media files and WordPress files and choosing an appropriate S3 provider can optimize traffic costs for websites with a substantial number of images.

Of course, separating media files from WordPress files is not mandatory. If your website doesn't involve a large quantity of images or videos, you can choose to skip this step.

## Cloudflare R2

We recommend storing your media files on Cloudflare R2, with zero outbound traffic fees and a highly advantageous monthly 10GiB of free storage space for small WordPress websites.

## Plugin

You can choose to integrate WordPress with Cloudflare R2 using the [Media Cloud plugin](https://wordpress.org/plugins/ilab-media-tools/).
