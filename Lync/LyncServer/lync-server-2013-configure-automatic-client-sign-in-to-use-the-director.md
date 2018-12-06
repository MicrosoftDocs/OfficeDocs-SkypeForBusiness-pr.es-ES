---
title: "Lync Server 2013: Config. inicio de sesión autom. de clientes para usar el director"
TOCTitle: Configurar el inicio de sesión automático de los clientes para usar el director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48275903
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar el inicio de sesión automático de los clientes para usar el director en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Al implementar Lync Server 2013, un director o un grupo de servidores de directores, le recomendamos que use el inicio de sesión automático de los clientes. Es uno de los procedimientos recomendados. Para ver más detalles acerca de cómo configurar servidores DNS para el inicio de sesión automático de los clientes, consulte [Requisitos DNS para inicio de sesión automática del cliente en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) en la documentación sobre planeación.

Si ya ha implementado el inicio de sesión automático de los clientes, consulte las siguientes secciones para configurarlo en sus directores.

## Instancia de director único

Si ya ha implementado el inicio de sesión automático de los clientes y está apuntando a un Servidor front-endo a un Grupo de servidores front-end, debe cambiar el registro DNS SRV de modo que apunte al director.

## Grupo de servidores de director

Si ya ha implementado el inicio de sesión automático de los clientes y está apuntando a un Servidor front-endo a un Grupo de servidores front-end, debe cambiar el registro DNS SRV de modo que apunte al grupo de directores.

