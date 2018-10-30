---
title: "Lync Server 2013: Preparación de los Servicios de dominio de Active Directory"
TOCTitle: Información general sobre la preparación de los Servicios de dominio de Active Directory
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48276692
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre la preparación de los Servicios de dominio de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para preparar Servicios de dominio de Active Directory para la implementación de Lync Server 2013, debe seguir tres pasos en una secuencia específica.

En la tabla siguiente se describen los pasos necesarios para preparar AD DS para Lync Server.

### Pasos de preparación de Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Paso</th>
<th>Descripción</th>
<th>Dónde se ejecuta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparación del esquema de Active Directory en Lync Server 2013</a></p></td>
<td><p>Extienda el esquema de Active Directory. Para ello, agregue las nuevas clases y atributos que usa Lync Server.</p>
<p>Ejecútelo una vez para cada bosque de la implementación donde se vaya a implementar Lync Server.</p></td>
<td><p>En el maestro de esquema del dominio raíz de cada bosque donde se vaya a implementar Lync Server.</p>
<div>

> [!NOTE]
> No es necesario realizar este paso en el dominio raíz si tiene permisos en el maestro de esquema, pero debe ser miembro de los grupos Administradores de esquema en el dominio raíz y Administradores de organización en el maestro de esquema. En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Preparación del bosque para Lync Server 2013</a></p></td>
<td><p>Crea la configuración global y los grupos universales que usa Lync Server.</p>
<p>Ejecútelo una vez para cada bosque de la implementación donde se vaya a implementar Lync Server.</p></td>
<td><p>En el dominio raíz de cada bosque donde se va a implementar Lync Server. Para llevar a cabo este paso, debe ser miembro del grupo Administradores de organización.</p>
<div>

> [!NOTE]
> En una topología de bosque de recursos, ejecute este paso solo en el bosque de recursos, no en los bosques de usuarios. En una topología de bosque central, ejecute este paso solo en el bosque central, no en los bosques de usuarios.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Preparar dominios para Lync Server 2013</a></p></td>
<td><p>Agrega permisos a los objetos que van a usar los miembros de grupos universales.</p>
<p>Ejecútelo una vez por dominio de usuario o dominio de servidor.</p>
<div>

> [!NOTE]
> Si va a migrar de Lync Server 2010 a Lync Server 2013, el Asistente para la implementación puede indicar que la preparación del dominio ya se ha completado. No necesita volver a ejecutar la preparación del dominio. Los permisos no se han cambiado de Lync Server 2010 a Lync Server 2013.


</div></td>
<td><p>En un servidor miembro en cada dominio donde se vaya a implementar Lync Server. Para llevar a cabo este paso, debe ser miembro del grupo de administradores del dominio.</p></td>
</tr>
</tbody>
</table>


En Lync Server 2013, como en Lync Server 2010, mucha de la información de configuración se almacena en Almacén de administración central, en lugar de en AD DS, como ocurría en Office Communications Server 2007 R2. No obstante, en AD DS se almacena la información siguiente:

  - **Extensiones de esquema**:
    
      - Extensiones de objetos de usuario
    
      - Extensiones para las clases de Office Communications Server 2007 R2 con el fin de mantener la compatibilidad con versiones anteriores.

<!-- end list -->

  - **Datos** (almacenados en el esquema extendido de Lync Server y en las clases de esquema existentes):
    
      - Identificador uniforme de recursos (URI) de SIP del usuario y otros parámetros de usuario
    
      - Objetos de contacto para aplicaciones como Grupo de respuesta y Operador de conferencia
    
      - Un puntero al Almacén de administración central
    
      - Cuenta de autenticación Kerberos (un objeto de equipo opcional)

En Lync Server 2013, se delegan las tareas de administración e instalación. Para ello, se conceden permisos de instalación al grupo universal RTCUniversalServerAdmins de forma que los miembros de dicho grupo pueden instalar y activar Lync Server 2013 en un servidor local (después de agregar, publicar y habilitar el servidor en la topología). Los usuarios delegados deben ser administradores locales en el equipo donde se va a instalar y activar Lync Server 2013, pero no es necesario que sean miembros del grupo de administradores del dominio. También puede conceder permisos para objetos en unidades organizativas (OU) especificadas, de modo que los miembros de los grupos universales que se crean durante la preparación del bosque pueden obtener acceso a los objetos sin ser miembros del grupo de administradores del dominio.

Para nuevas implementaciones de Lync Server 2013, la configuración global debe almacenarse en el contenedor de configuración. Si su organización se va actualizar desde una versión anterior y todavía tiene la configuración global en el contenedor del sistema, el contenedor del sistema seguirá siendo compatible.

## Vea también

#### Conceptos

[Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  

#### Otros recursos

[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)

