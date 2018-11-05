---
title: Validar direcciones
TOCTitle: Validar direcciones
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48276321
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Validar direcciones

 

_**Última modificación del tema:** 2012-09-17_

Antes de publicar la base de datos de las ubicaciones, debe validar las nuevas ubicaciones comparándolas con la guía de direcciones que mantiene el proveedor de servicios de emergencia.

Para más información sobre los proveedores de servicios de emergencia, consulte [Selección de un proveedor de servicios E9-1-1 en Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md).

Para más información sobre la validación de direcciones, consulte la documentación del Shell de administración de Lync Server para los siguientes cmdlets:

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

## Para validar direcciones ubicadas en la base de datos de ubicaciones

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para configurar la conexión de proveedor de servicios de emergencia, ejecute los siguientes cmdlets.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  Para validar las direcciones en la base de datos de ubicaciones, ejecute el siguiente cmdlet.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    También puede usar el cmdlet **Test-CsLisCivicAddress** para validar direcciones individuales.

