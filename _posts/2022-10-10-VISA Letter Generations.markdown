---
layout: post
title:  "VISA Letter Generations"
date:   2022-10-10 22:30:39 +0530
categories: ideation forms
---

# VISA Letter Generations

## Business Case

Streamline the approval mechanism for international business travel so that VISA generation can be handled by a department.
Depending on the country to visit the format and mandatory documents vary.
The process aims to simplify the generation process by simplifying the genration process and formats from the user and make the journey more user friendly.
Having a process also helps in adapting to the ever changing policies.

```mermaid
journey
    title VISA Letter Generation Streamline
    section Plan Trip
      Fill Travel Details: 2: Employee
      Approval and Verification: 3: Line Manager, Employee
      Plan The Travel: 4: Travel Manager, Employee
      Document Submission: 4: Travel Manager, Employee
      VISA Stamping: 5: Employee
		
```


## Fusion System Components



### Request
```xml

<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:pub="http://xmlns.oracle.com/oxp/service/PublicReportService">
   <soap:Header/>
   <soap:Body>
      <pub:uploadReportDataChunk>
         <pub:fileID>XX123</pub:fileID>
         <pub:reportDataChunk>PE1BSU5EUz4KPERBVEE+VGhpcyBpcyBmcm9tIGxvY2FsIGZpbGU8L0RBVEE+CjwvTUFJTkRTPg==</pub:reportDataChunk>
<!--         <pub:reportRawDataChunk>?</pub:reportRawDataChunk>
-->
      </pub:uploadReportDataChunk>
   </soap:Body>
</soap:Envelope>


```

### Response

```xml
<env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope">
   <env:Header/>
   <env:Body>
      <ns2:uploadReportDataChunkResponse xmlns:ns2="http://xmlns.oracle.com/oxp/service/PublicReportService">
         <ns2:uploadReportDataChunkReturn>XX123</ns2:uploadReportDataChunkReturn>
      </ns2:uploadReportDataChunkResponse>
   </env:Body>
</env:Envelope>
```

### Request

```xml
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:pub="http://xmlns.oracle.com/oxp/service/PublicReportService">
   <soap:Header/>
   <soap:Body>
      <pub:runReport>
         <pub:reportRequest>
            <pub:XDOPropertyList>
               <!--Zero or more repetitions:-->
               <pub:metaDataList>
                  <!--Optional:-->
                  <pub:name></pub:name>
                  <!--Optional:-->
                  <pub:value></pub:value>
               </pub:metaDataList>
            </pub:XDOPropertyList>
            <pub:attributeCalendar></pub:attributeCalendar>
            <pub:attributeFormat>pdf</pub:attributeFormat>
            <pub:attributeLocale></pub:attributeLocale>
            <pub:attributeTemplate>DUMMY</pub:attributeTemplate>
            <pub:attributeTimezone></pub:attributeTimezone>
            <pub:attributeUILocale></pub:attributeUILocale>
            <pub:byPassCache></pub:byPassCache>
            <pub:dynamicDataSource>
               <pub:JDBCDataSource>
                  <pub:JDBCDriverClass></pub:JDBCDriverClass>
                  <pub:JDBCDriverType></pub:JDBCDriverType>
                  <pub:JDBCPassword></pub:JDBCPassword>
                  <pub:JDBCURL></pub:JDBCURL>
                  <pub:JDBCUserName></pub:JDBCUserName>
                  <pub:dataSourceName></pub:dataSourceName>
               </pub:JDBCDataSource>
               <pub:fileDataSource>
                  <pub:dynamicDataSourcePath>XX123</pub:dynamicDataSourcePath>
                  <pub:temporaryDataSource>true</pub:temporaryDataSource>
               </pub:fileDataSource>
            </pub:dynamicDataSource>
            <pub:flattenXML></pub:flattenXML>
            <pub:parameterNameValues>
               <!--Zero or more repetitions:-->
               <pub:item>
                  <pub:UIType></pub:UIType>
                  <pub:dataType></pub:dataType>
                  <pub:dateFormatString></pub:dateFormatString>
                  <pub:dateFrom></pub:dateFrom>
                  <pub:dateTo></pub:dateTo>
                  <pub:defaultValue></pub:defaultValue>
                  <pub:fieldSize></pub:fieldSize>
                  <pub:label></pub:label>
                  <pub:lovLabels>
                     <!--Zero or more repetitions:-->
                     <pub:item></pub:item>
                  </pub:lovLabels>
                  <pub:multiValuesAllowed></pub:multiValuesAllowed>
                  <pub:name></pub:name>
                  <pub:refreshParamOnChange></pub:refreshParamOnChange>
                  <pub:selectAll></pub:selectAll>
                  <pub:templateParam></pub:templateParam>
                  <pub:useNullForAll></pub:useNullForAll>
                  <pub:values>
                     <!--Zero or more repetitions:-->
                     <pub:item></pub:item>
                  </pub:values>
               </pub:item>
            </pub:parameterNameValues>
            <pub:reportAbsolutePath>/Custom/DUMMY/DUMMY.xdo</pub:reportAbsolutePath>
<!--            <pub:reportData>cid:1010680060983</pub:reportData>-->
            <pub:reportOutputPath></pub:reportOutputPath>
            <pub:reportRawData></pub:reportRawData>
            <pub:sizeOfDataChunkDownload>-1</pub:sizeOfDataChunkDownload>
         </pub:reportRequest>
         <pub:appParams></pub:appParams>
      </pub:runReport>
   </soap:Body>
</soap:Envelope>
```

### Response

```xml

<env:Envelope xmlns:env="http://www.w3.org/2003/05/soap-envelope">
   <env:Header/>
   <env:Body>
      <ns2:runReportResponse xmlns:ns2="http://xmlns.oracle.com/oxp/service/PublicReportService">
         <ns2:runReportReturn>
            <ns2:reportBytes>JVBERi0xLjYNCjUgMCBvYmoNCjw8DQovVHlwZSAvUGFnZQ0KL1BhcmVudCAzIDAgUg0KL1Jlc291cmNlcyA0IDAgUg0KL0NvbnRlbnRzIDYgMCBSDQovTWVkaWFCb3hbIDAgMCA2MTIuMCA3OTIuMCBdDQovQ3JvcEJveFsgMCAwIDYxMi4wIDc5Mi4wIF0NCi9Sb3RhdGUgMA0KPj4NCmVuZG9iag0KNiAwIG9iag0KPDwgL0xlbmd0aCA4OCAvRmlsdGVyIC9GbGF0ZURlY29kZSA+Pg0Kc3RyZWFtDQp4nDNQMADCIHcwZaBQlM7L5RTCy2UI5hkqGJspmJuY6ZkZK4Tk8nLpuxnycikYGiiEpPFyaYRkZBYrAFFaUX6uQk5+cmKOQlpmTqpmSBYvlyvQDABJNhSKDQplbmRzdHJlYW0NCmVuZG9iag0KMSAwIG9iag0KPDwNCi9UeXBlIC9DYXRhbG9nDQovUGFnZXMgMyAwIFINCj4+DQplbmRvYmoNCjIgMCBvYmoNCjw8DQovVHlwZSAvSW5mbw0KL1Byb2R1Y2VyIChPcmFjbGUgQW5hbHl0aWNzIFB1Ymxpc2hlcikNCj4+DQplbmRvYmoNCjMgMCBvYmoNCjw8DQovVHlwZSAvUGFnZXMNCi9LaWRzIFsNCjUgMCBSDQpdDQovQ291bnQgMQ0KPj4NCmVuZG9iag0KNCAwIG9iag0KPDwNCi9Qcm9jU2V0IFsgL1BERiAvVGV4dCBdDQovRm9udCA8PCANCi9GMSA3IDAgUg0KPj4NCj4+DQplbmRvYmoNCjcgMCBvYmoNCjw8DQovVHlwZSAvRm9udA0KL1N1YnR5cGUgL1R5cGUxDQovQmFzZUZvbnQgL0hlbHZldGljYQ0KL0VuY29kaW5nIC9XaW5BbnNpRW5jb2RpbmcNCj4+DQplbmRvYmoNCnhyZWYNCjAgOA0KMDAwMDAwMDAwMCA2NTUzNSBmDQowMDAwMDAwMzMzIDAwMDAwIG4NCjAwMDAwMDAzODggMDAwMDAgbg0KMDAwMDAwMDQ2NiAwMDAwMCBuDQowMDAwMDAwNTM0IDAwMDAwIG4NCjAwMDAwMDAwMTAgMDAwMDAgbg0KMDAwMDAwMDE2OCAwMDAwMCBuDQowMDAwMDAwNjEwIDAwMDAwIG4NCnRyYWlsZXINCjw8DQovU2l6ZSA4DQovUm9vdCAxIDAgUg0KL0luZm8gMiAwIFINCi9JRCBbPGViOWU3OWEzNmRmMjg2OTljNmNiMTJjYTE0MDdlZDU4MzEyMTAwNGVlN2QyNzc4NjczM2I2ZmM0YzhiNzlhODY+PGViOWU3OWEzNmRmMjg2OTljNmNiMTJjYTE0MDdlZDU4MzEyMTAwNGVlN2QyNzc4NjczM2I2ZmM0YzhiNzlhODY+XQ0KPj4NCnN0YXJ0eHJlZg0KNzE1DQolJUVPRg0K</ns2:reportBytes>
            <ns2:reportContentType>application/pdf</ns2:reportContentType>
            <ns2:reportFileID xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"/>
            <ns2:reportLocale xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"/>
            <ns2:metaDataList xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"/>
         </ns2:runReportReturn>
      </ns2:runReportResponse>
   </env:Body>
</env:Envelope>
```


```mermaid
graph TD
USR[User] --> PDF
PDF[PDF] --> UCM[UCM]
UCM[UCM] --> DOR[DOR]
DOR[DOR] --> BPM[Approval]
linkStyle default fill: none, stroke: grey
```

    <!--- your comment goes here and here -->
    