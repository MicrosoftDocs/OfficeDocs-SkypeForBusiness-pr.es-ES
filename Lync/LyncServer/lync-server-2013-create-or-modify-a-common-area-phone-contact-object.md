---
title: Crear o modificar un objeto de contacto de teléfono de área común
TOCTitle: Crear o modificar un objeto de contacto de teléfono de área común
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994083(v=OCS.15)
ms:contentKeyID: 52061962
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Crear o modificar un objeto de contacto de teléfono de área común

 

_**Última modificación del tema:** 2013-02-20_

Use el cmdlet **New-CsCommonAreaPhone** para crear objetos de contacto de Servicios de dominio de Active Directory para todos los teléfonos de área común. Con este cmdlet se pueden crear objetos de contacto para usarlos con teléfonos de área común, o bien asociar objetos de contacto existentes a nuevos teléfonos de área común. Use el cmdlet **Set-CsCommonAreaPhone** para modificar las propiedades de los objetos de contacto asociados con los teléfonos de área común. Hay otros parámetros opcionales para **Set-CsCommonAreaPhone** que permiten cambiar elementos (como el nombre para mostrar de Active Directory del contacto o el Identificador uniforme de recursos (URI) de línea asociado al teléfono), así como habilitar o deshabilitar la cuenta para usarla con Lync Server. Para más información sobre las modificaciones disponibles, vea la sección de parámetros en [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone). Para más información sobre los parámetros de **New-CsCommonAreaPhone**, vea [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone).

Estos dos cmdlets se pueden ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Crear un objeto de contacto de teléfono de área común

  - Use el cmdlet **New-CsCommonAreaPhone** para crear un objeto de contacto de teléfono de área común. Al crear un objeto de contacto, debe proporcionar la siguiente información como mínimo:
    
      - **LineUri**: número de teléfono asignado al teléfono de área común. No olvide que tiene que usar el formato E.164 al especifica este número de teléfono.
    
      - **RegistrarPool**: nombre de dominio completo (FQDN) del grupo de registradores que va a hospedar el objeto de contacto.
    
      - **OU**: nombre distintivo del contenedor de Active Directory donde se va a crear el objeto de contacto.
    
    También es aconsejable proporcionar un nombre para mostrar de Servicios de dominio de Active Directory o, de lo contrario, deberá usar un GUID para indicar la identidad del teléfono. Por ejemplo:
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

## Modificar un objeto de contacto de teléfono de área común

  - Use el cmdlet **Set-CsCommonAreaPhone** para modificar las propiedades de un teléfono de área común existente. Por ejemplo, con este comando se configura la dirección SIP del teléfono de área común con el nombre para mostrar Lobby:
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

Para ver detalles, consulte los temas de ayuda relativos a los cmdlets [New-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCommonAreaPhone) y [Set-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCommonAreaPhone).

