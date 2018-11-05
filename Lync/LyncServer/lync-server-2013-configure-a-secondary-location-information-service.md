---
title: Configurar un servicio de información de ubicación secundario en Lync Server 2013
TOCTitle: Configurar un servicio de información de ubicación secundario en Lync Server 2013
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48274346
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar un servicio de información de ubicación secundario en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-30_

Lync Server 2013 proporciona una interfaz de servicios web que puede usar para orientar el Servicio de información de ubicaciones a una base de datos de Origen de ubicación secundario (SLS). La interfaz de servicios web que se conecta a la base de datos SLS debe ajustarse al WSDL del Servicio de información de ubicaciones. Si se ha configurado tanto la base de datos de ubicación como la base de datos de ubicación secundaria, el Servicio de información de ubicaciones consultará en primer lugar a la base de datos de ubicación y, si no obtiene ninguna coincidencia, enviará la solicitud de ubicación del cliente a la base de datos SLS. Si la ubicación existe en el SLS, el Servicio de información de ubicaciones devolverá la ubicación al cliente.

Para obtener más información, consulte la documentación de Shell de administración de Lync Server para el siguiente cmdlet:

  - **Set-CsWebServiceConfiguration**

## Para configurar la base de datos de ubicación secundaria

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el siguiente cmdlet para configurar la URL para la ubicación de la base de datos de ubicación secundaria.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>"

