# custom_component to update Cloudflare records
![Version](https://img.shields.io/badge/version-2.0.1-green.svg?style=for-the-badge)
  
A component which allows you to update the IP adderesses of your Cloudflare DNS records.
  
To get started put `/custom_components/cloudflare.py` here:
`<config directory>/custom_components/cloudflare.py`  
  
**Example configuration.yaml:**
```yaml
cloudflare:
  email: 'user@example.com'
  key: 'c2547eb745079dac9320b638f5e225cf483cc5cfdda41'
  records: 'bin', 'www'
  zone: 'example.com'
```
**Configuration variables::**  
**email (Required)**: null  
**key (Required)**: null  
**zone (Required)**: null  
**records (Optional)**: null  
You will find your global API `key` in your cloudflare account settings.
The component will run every hour, but can also be manually started by using the service `cloudflare.update_records` under services.  
This component uses the API from [ipify.org](https://www.ipify.org/) to set the public IP address.