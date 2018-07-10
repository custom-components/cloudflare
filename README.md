# custom_component to update Cloudflare records

A platform which allows you to update the IP adderesses of your Cloudflare DNS records.

## [PR for merging this with Home Assistant](https://github.com/home-assistant/home-assistant/pull/15388)
  
To get started put `/custom_components/cloudflare.py`  
here: `<config directory>/custom_components/cloudflare.py`  
  
**Example configuration.yaml:**

```yaml
cloudflare:
  email: user@example.com
  api_key: c2547eb745079dac9320b638f5e225cf483cc5cfdda41
  zone: example.com
  records:
    - bin
    - www
```

**Configuration variables:**  
  
key | description  
:--- | :---  
**email (Required)** | The email address for your Cloudflare account.  
**key (Required)** | The global API key for your Cloudflare account.  
**zone (Required)** | The DNS zone you want to update.  
**records (Required)** | A list of records you want to update.
  
You will find your global API `key` in your cloudflare account settings.
The component will run every hour, but can also be manually started by using the service `cloudflare.update_records` under services.  
This platform uses the API from [ipify.org](https://www.ipify.org/) to set the public IP address.  
***
Due to how `custom_componentes` are loaded, it is normal to see a `ModuleNotFoundError` error on first boot after adding this, to resolve it, restart Home-Assistant.