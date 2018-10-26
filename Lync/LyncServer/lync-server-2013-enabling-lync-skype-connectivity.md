---
title: 'Lync Server 2013: Activar la conectividad entre Lync y Skype'
TOCTitle: Activar la conectividad entre Lync y Skype
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn440170(v=OCS.15)
ms:contentKeyID: 59602829
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activar la conectividad entre Lync y Skype en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Después de enviar la solicitud de aprovisionamiento, se puede centrar en el entorno de Lync Server y en las tareas administrativas necesarias para configurar la conectividad entre Lync y Skype. En esta sección, presuponemos que el administrador de Lync Server ha implementado Lync Server y ha configurado el acceso externo. Para información adicional sobre cómo configurar el acceso externo en Lync Server, vea [Planear acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) y [Implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Para preparar el entorno de Lync Server para la conectividad entre Lync y Skype, el administrador de Lync Server debe completar las tres tareas siguientes:

## 1\. Configurar la federación y la PIC

La federación es necesaria para permitir a los usuarios de Skype que se comuniquen con los usuarios de Lync de su organización. Public Instant Messaging Connectivity (PIC), que es un tipo de federación, se debe configurar para que los usuarios de Lync se puedan comunicar con los usuarios de Skype. La federación y la PIC se configuran usando el panel de control de Lync Server, que verá abajo.

![Mostrando PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Mostrando PIC")

> [!IMPORTANT]  
> La federación PIC ya no es compatible con Live Communication Server 2005 SP1 ni con Office Communications Server 2007. Las plataformas compatibles para la federación PIC incluyen Lync Server 2013, Lync Server 2010 y Office Communications Server 2007 R2.



## 2\. Configurar al menos una directiva para permitir el acceso de usuarios federados

Los administradores tienen que configurar una o varias directivas de acceso de usuarios externos desde el panel de control de Lync Server para controlar si los usuarios de Skype pueden colaborar con usuarios internos de Lync Server.

![Directivas](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Directivas")

## 3\. Establecer la configuración del proveedor de PIC para Lync

En el Shell de administración de Lync Server, los administradores pueden configurar la directiva de cliente de Lync para mostrar Skype como un proveedor de PIC adicional.


> [!NOTE]
> Los usuarios de los proveedores de servicios Public Instant Messaging Connectivity (PIC) no pueden participar en conferencias de vídeo, audio o mensajería instantánea en su organización hasta que configure también una política (paso 2, anteriormente en este procedimiento) para que el servicio sea compatible con la conectividad de mensajería instantánea pública.



1.  Para configurar la federación y la PIC, vea "Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública" en [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063).

2.  Para configurar al menos una directiva para admitir el acceso de usuarios federados, vea "Configuración de directivas para controlar el acceso de usuarios públicos" en [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064).

**Para editar un proveedor de Messenger PIC y configurarlo para Skype**

1.  Desde un servidor front-end de Lync Server, abra el Shell de administración de Lync Server.

2.  Ejecute estos dos comandos:
    
    `Remove-CsPublicProvider -Identity Messenger`
    
    `New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png" -VerificationLevel 2 -Enabled 1`

3.  Desde un cliente de Lync, puede seleccionar Skype como el proveedor de PIC y añadir un cliente de Skype especificando una cuenta Microsoft. Además, un usuario de Skype que haya combinado e iniciado sesión con su cuenta de Microsoft puede enviar una solicitud de contacto a usuarios de Lync. Para obtener más información sobre las cuentas Microsoft, consulte [¿Qué es una cuenta Microsoft?](https://support.skype.com/es/faq/fa12059/what-is-a-microsoft-account). Para obtener más información de cómo añadir clientes a Lync, consulte [Usar la conectividad de Lync y Skype como usuario final en Lync Server 2013](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Agregar contacto de Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Agregar contacto de Skype")

4.  Para información detallada sobre cómo modificar proveedores hospedados, vea "Creación o edición de proveedores federados de SIP hospedados" en [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065).

Estas son todas las tareas administrativas que se deben llevar a cabo en el servidor. Ahora ya está todo configurado para la conectividad entre Lync y Skype.

