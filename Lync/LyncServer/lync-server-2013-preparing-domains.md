---
title: 'Lync Server 2013: Preparar dominios'
TOCTitle: Preparar dominios
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48275992
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparar dominios para Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

La preparación del dominio es el último paso de la preparación de Servicios de dominio de Active Directory para Lync Server 2013. El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.

Puede ejecutar la preparación del dominio en cualquier equipo del dominio donde esté implementando Lync Server. Debe preparar todos los dominios que hospedarán usuarios o Lync Server.

Si la herencia de permisos está deshabilitada o los permisos de usuarios autenticados están deshabilitados en su organización, hay pasos adicionales que debe realizar durante la preparación de los dominios. Para ver más detalles, consulte [Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

Si en su organización se usan unidades organizativas (OU) en lugar de los tres contenedores integrados (es decir, usuarios, equipos y controladores de dominio), debe conceder acceso de lectura de las OU al grupo Usuarios autenticados. El acceso de lectura de los contenedores se necesita para preparar dominios. Si el grupo Usuarios autenticados no tiene acceso de lectura de la OU, ejecute el cmdlet **Grant-CsOuPermission** según se indica en los siguientes códigos de ejemplo, para conceder permisos de lectura a cada OU.

```
Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
```
```
Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
```

Para ver los detalles sobre el cmdlet **Grant-CsOuPermission**, consulte la documentación de Shell de administración de Lync Server.

> [!TIP]  
> Para obtener detalles sobre las ACE creadas en la raíz del dominio y en los contenedores de usuarios, equipos y controladores de dominio, consulte <a href="lync-server-2013-changes-made-by-domain-preparation.md">Cambios realizados por la preparación del dominio en Lync Server 2013</a>.



## En esta sección

  - [Ejecutar la preparación del dominio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Uso de cmdlets para revertir la preparación del dominio para Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

