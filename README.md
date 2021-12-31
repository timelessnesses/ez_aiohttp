# ez_aiohttp
The aiohttp wrapper to make it more like requests.

# How to use
It is kinda like requests, but it is async.
And you need to import aiohttp if you want to use more than GET,POST,PUT,PATCH,DELETE.  
This just make it more simple.  
Here's an example:
```py
import aiohttp,ez_rq,ez_rq.util

async def main():
    a = ez_rq.get('https://www.google.com')
    print(await a.text())
    b = ez_rq.post('https://www.google.com',data={'a':'b'})
    print(await b.text())
    c = ez_rq.put('https://www.google.com',data={'a':'b'})
    print(await c.text())
    d = ez_rq.patch('https://www.google.com',data={'a':'b'})
    print(await d.text())
    e = ez_rq.delete('https://www.google.com')
    print(await e.text())
    f = await ez_rq.util.json2attr(a) # or you can send the dictionary
    f.a = 'b'
    print(await ez_rq.util.attr2json(f))
```
etc.  
It always return `aiohttp.client_reqrep.ClientResponse` object.  
[doc](https://ez-aiohttp.rukchadisa.live/en/latest/)