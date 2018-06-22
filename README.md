# custom_component to update Cloudflare records
  
![Version](https://img.shields.io/badge/version-2.0.1-green.svg?style=for-the-badge) ![mantained](https://img.shields.io/maintenance/yes/2018.svg?style=for-the-badge) A platform which allows you to update the IP adderesses of your Cloudflare DNS records.
  
To get started put `/custom_components/cloudflare.py`  
here: `<config directory>/custom_components/cloudflare.py`  
  
**Example configuration.yaml:**
```yaml
cloudflare:
  email: 'user@example.com'
  key: 'c2547eb745079dac9320b638f5e225cf483cc5cfdda41'
  zone: 'example.com'
  records:
    - 'bin'
    - 'www'
```
**Configuration variables:**  
  
key | description  
:--- | :---  
**email (Required)** | The email address for your Cloudflare account.  
**key (Required)** | The global API key for your Cloudflare account.  
**zone (Required)** | The DNS zone you want to update.  
**records (Optional)** | A list of records you want to update, if no list are defined if will update every A record in that zone.  
  
You will find your global API `key` in your cloudflare account settings.
The component will run every hour, but can also be manually started by using the service `cloudflare.update_records` under services.  
This platform uses the API from [ipify.org](https://www.ipify.org/) to set the public IP address.