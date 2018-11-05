---
title: 'Lync Server 2013: Directivas de correo de voz hospedado'
TOCTitle: Directivas de correo de voz hospedado
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48276811
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Directivas de correo de voz hospedado en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Una *directiva de correo de voz hospedada* proporciona información a la aplicación Lync Server 2013 ExUM Routing sobre a dónde redirigir las llamadas para usuarios cuyos buzones se encuentren en un servicio de Exchange hospedado.


> [!NOTE]
> Las directivas de correo de voz hospedado solo son necesarias para la integración de Lync Server 2013 con la mensajería unificada hospedada de Exchange. No son necesarias para la integración con la mensajería unificada local de Exchange.



## Ámbito de directiva de correo de voz hospedado

El ámbito de directiva de correo de voz hospedado determina el nivel jerárquico en que se aplica la directiva. Configure directivas de correo de voz hospedado con los niveles de ámbito siguientes:

  - La directiva *global* puede afectar a todos los usuarios de la implementación de Lync Server 2013. Si un usuario está habilitado para el acceso a la mensajería unificada hospedada de Exchange y no se le ha asignado una directiva por usuario, y si no se ha asignado una directiva de sitio al sitio del usuario, se aplicará la directiva global. La directiva global se instala junto con Lync Server 2013. Modifíquela para adaptarla a sus necesidades, aunque no puede cambiarle el nombre ni eliminarla.

  - Una directiva de *sitio* puede afectar a todos los usuarios que están hospedados en el sitio para el que se ha definido la directiva. Si un usuario está configurado para el acceso a la mensajería unificada hospedada de Exchange y no se le ha asignado una directiva por usuario, se aplicará la directiva de sitio.

  - Una directiva *por usuario* solo afecta a grupos o usuarios individuales. Para aplicar una directiva por usuario, debe asignar de forma explícita la directiva a objetos de contacto, usuarios y grupos.


> [!NOTE]
> En la mayoría de los casos, solo es necesaria una directiva de correo de voz hospedado. Por lo general, es posible modificar la directiva global para adaptarla a nuestras necesidades específicas. Si implementa varias directivas de correo de voz hospedado, todas estas directivas serán de ámbito por usuario.



## Atributos de directiva de correo de voz hospedado

Las directivas de correo de voz definen dos atributos que la aplicación de enrutamiento de mensajería unificada de Exchange de Lync Server 2013 inserta en el URI de la solicitud de un mensaje INVITE que se envía a la implementación de mensajería unificada hospedada de Exchange:

  - **Destination :** el nombre de dominio completo (FQDN) del servicio de mensajería unificada hospedada de Exchange. El servidor perimetral local de Lync Server usa este valor para el enrutamiento.
    

    > [!NOTE]
    > El FQDN para Exchange Online es exap.um.outlook.com.



  - **Organization:** el FQDN del arrendatario en el servicio de mensajería unificada hospedada de Exchange donde se encuentran los buzones de correo de los usuarios de Lync Server 2013. Una directiva de correo de voz puede contener varias organizaciones. Si la directiva contiene más de una organización, este atributo debe ser una lista de los arrendatarios de Exchange Server donde se encuentran los buzones de correo de usuarios de Lync Server 2013 separados por comas.


> [!NOTE]
> El administrador de arrendatarios del servicio de mensajería unificada hospedada de Exchange proporcionará los valores necesarios para la configuración de los atributos Destination y Organization. Para configurar su directiva, ejecute el cmdlet New-CsHostedVoicemailPolicy o use el cmdlet Set-CsHostedVoicemailPolicy para modificar una que ya exista (por ejemplo, la directiva global).



Para más información sobre la administración de directivas de correo de voz hospedado, consulte la documentación del Shell de administración de Lync Server para los siguientes cmdlets:

  - New-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - Get-CsHostedVoicemailPolicy

## Asignación de directivas de correo de voz por usuario

Si su directiva de correo de voz hospedado se ha definido con el ámbito por usuario, asígnela de forma explícita. Puede ejecutar el cmdlet Grant-CsHostedVoicemailPolicy para asignar la directiva a grupos o usuarios individuales.

Para obtener información detallada sobre la asignación o la eliminación de una directiva de correo de voz hospedada por usuario, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

