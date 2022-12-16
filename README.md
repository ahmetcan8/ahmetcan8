import requests

url = "https://tckimlik.nvi.gov.tr/Service/KPSPublic.asmx?WSDL"
headers = {'content-type': 'text/xml'}

body = """<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <TCKimlikNoDogrula xmlns="http://tckimlik.nvi.gov.tr/WS">
      <TCKimlikNo>TCNUMARASI</TCKimlikNo>
      <Ad>ADIN</Ad>
      <Soyad>SOYADIN</Soyad>
      <DogumYili>DOGUMYILIN</DogumYili>
    </TCKimlikNoDogrula>
  </soap:Body>
</soap:Envelope>"""

r = requests.post(url,data=body,headers=headers)
print r.content # 
TurhanErgene commented on Sep
