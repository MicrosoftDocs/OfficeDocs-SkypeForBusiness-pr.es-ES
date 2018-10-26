---
title: Problemas con la prueba de topología
TOCTitle: Problemas con la prueba de topología
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48275850
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Problemas con la prueba de topología

 

_**Última modificación del tema:** 2012-09-21_

Como el cmdlet **Test-CsTopology**, el Analizador de procedimientos recomendados proporciona una forma para que verifique que Lync Server 2013 funcione correctamente a nivel global. De forma predeterminada, el Analizador de procedimientos recomendados, como el cmdlet, revisa toda su infraestructura Lync Server 2013, verificando que los servicios requeridos estén funcionando, y que se hayan configurado los permisos y derechos de usuario correspondientes parra estos servicios y para los grupos universales de seguridad al instalar Lync Server 2013.

Además de verificar la validez de Lync Server en su totalidad, **Test-CsTopology** también revisa la validez de un servicio específico. Para obtener detalles sobre el uso del cmdlet para probar servicios específicos, vea [Test-CsTopology](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTopology) en la documentación de Shell de administración de Lync Server. Use la siguiente información para ayudar a resolver los problemas con su topología.


> [!NOTE]
> Dependiendo de la configuración de sus Servidores perimetrales y las configuraciones de red perimetrales relacionadas, incluso los permisos y configuraciones de firewall, el Analizador de mejores prácticas puede no acceder y registrar sus Servidores perimetrales. Si incluye los Servidores perimetrales en su registro y los informes indican que existe un problema al acceder a los Servidores perimetrales, desmarque la casilla <STRONG>Servidores perimetrales</STRONG> y ejecute nuevamente para evitar que el problema aparezca en los informes.



## Resolver problemas con su topología

Si la prueba de topología encuentra problemas con su topología, estos problemas son probablemente causados por problemas que se produjeron cuando publicó o habilitó su topología.

Cuando realiza cambios en su topología, los cambios surten efecto solo después de haberse publicado y habilitado. Debe usar la Generador de topologías para realizar cambios a la topología. Después de realizar los cambios, puede publicar y habilitar los cambios usando la Generador de topologías.

Cuando publica los cambios, la nueva información (como un nuevo sitio o un nuevo rol) se escribe en el Almacén de administración central. Sin embargo, estos nuevos objetos (o los que se modificaron recientemente) no se unen inmediatamente a su topología. los objetos se unen a su topología solo cuando habilita la topología actualizada. Si selecciona la opción Publicar en Generador de topologías se producen estos dos pasos: se publican los cambios (es decir, se escriben en el Almacén de administración central) y luego se habilita la nueva topología.

De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins tienen la autorización de ejecutar el cmdlet **Publish-CsTopology** y el cmdlet **Enable-CsTopology**. Sin embargo, si no se delegaron los permisos de configuración, debe haber iniciado sesión como un administrador de dominio para ejecutar **Publish-CsTopology**. Para proporcionar a RTCUniversalServerAdmins los derechos para usar el cmdlet **Publish-CsTopology** deberá ejecutar el cmdlet **Grant-CsSetupPermission** en todos los contenedores de Active Directory que contengan PC ejecutando servicios Lync Server. Para proporcionar a RTCUniversalServerAdmins el derecho a usar le cmdlet **Enable-CsTopology**, debe ejecutar el cmdlet **Set-CsSetupPermission** para todos los contenedores de Servicios de dominio de Active Directory que contienen los PC que están ejecutando servicios Lync Server. Tenga en cuenta que esto se aplica a la habilitación y publicación de una topología al usar Generador de topologías. Si no delegó permisos usando **Set-CsSetupPermission**, solo un administrador de dominio podrá habilitar y publicar una topología mediante Generador de topologías.

