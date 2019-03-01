---
layout: default
no_sidebar: true
title: Software
group: software

category:
  - name: NFD
    id: nfd
    icon: fa-info
    intro: "NDN Forwarding Daemon (NFD) is the reference implementation of the NDN protocol. The main functionality of NFD is to forward Interest and Data packets: it abstracts the lower-level network transport mechanisms into NDN Faces, maintains basic data structures such as the Content Store (CS), Pending Interest Table (PIT), and Forwarding Information Base (FIB), and implements the packet forwarding logic. NFD supports multiple strategies to forward interests and also implement several management interfaces for applications to configure, control, and monitor NFD. NFD was first released in August 2014, and the current version runs on OSX, Linux and FreeBSD."
    link: "http://named-data.net/doc/NFD/current/"

  - name: NLSR
    id: nlsr
    icon: fa-wifi
    intro: "A routing protocol is essential to running networks, either in the real world or in simulated/emulated environments. The Named-data Link State Routing Protocol (NLSR) supports name-based routing in NDN. It differs from traditional IP-based link-state routing protocols in that: (1) it uses NDN’s Interest/Data packets to exchange routing messages; (2) its route computation ranks all policy-compliant next-hops, providing a name-based multipath routing table for NDN’s forwarding strategy; and (3) it ensures that routers can originate only their own routing updates using a hierarchical trust model"
    link: "http://named-data.net/doc/NLSR/current/"

  - name: ndnSIM
    id: sim
    icon: fa-camera-retro
    intro: "ndnSIM is an open-source NDN stack simulator based on NS-3 framework. The core component of the simulator is an implementation of the NDN protocol stack, driven by the NFD and ndn-cxx source code. The ndnSIM-specific routines provide redirection routines to send/receive packets to/from the simulated environment, as well as numerous helpers and tracing points to simplify the setup of evaluation scenarios, and to help obtain and process results. The convergence of the simulation framework with the real forwarder and library implementation enables researchers to run large-scale high-fidelity evaluations that cover a large range of NDN aspects. An incomplete list of possible evaluation directions include experimentation with forwarding strategies, routing protocols, caching algorithms, application behavior, security, and cryptography schemes. It is possible to simulate a real NDN deployment on mobile, vehicular, peer-to-peer, ad-hoc, and IoT environments. In addition to that, it is also possible to run flexible experimentation of real applications written against the ndn-cxx library, provided the applications satisfy (or can be adapted to satisfy) a small set of simulation-enabling requirements."
    link: "http://ndnsim.net/current/"

  - name: miniNDN
    id: mini
    icon: fa-user-secret
    intro: "Mini-NDN is an NDN emulation tool based on Mininet. It provides a lightweight virtualized environment to run NFD and NDN applications. In Mini-NDN, an entire experiment runs on a single machine, and each node in the network topology is executed in a container with its own resources Moreover, there is a central point to control all the nodes via a python API provided by Mininet, making it easy to program large experiments. Although we have used Mini-NDN to primarily test our routing protocol NLSR, we would like to develop it as a comprehensive testing and experimentation tool for any NDN component and application."
    link: "http://minindn.memphis.edu/"

  - name: NDN-CCL
    id: ccl
    icon: fa-rocket
    intro: "Libraries provide the means for application developers to actually use the NDN architecture in both exploratory applications and those intended to achieve real-world goals. They are thus an important area of software development focus in this proposal. In this project, our effort is oriented towards turning research results and software prototypes into well-documented, robust tools for experimentation by others. The NDN project provides libraries for application developers in C++, Java, Javascript, and Python through ndn-cxx and the NDN Common Client Libraries (CCL)"
    link: "https://named-data.net/codebase/platform/ndn-ccl/"


  - name: NDN IoT Package
    id: iot
    icon: fa-rocket
    intro: "NDN IoT package aims at providing a m-in-one package for those who want to try a new networking protocol, the Named Data Networking (NDN), with their IoT apps on constrained devices, e.g., Nordic nRF58240 boards. Here 'm' stands for the following 4 parts, from bottom to top: (1) communication adaptation layer, which handles different communication mediums with the support from operating system (like RIOT), software development kit (like Nordic SDK), or even the raw device drivers; (2) basic NDN layer, which offers basic networking layer functionalities, including the basic security support, following the latest NDN specification; (3) application support layer, which includes some useful building blocks to NDN applications, such as security bootstraping, service discover as well as access control; (4) an example application, where two parties are involved: a network controller (runs on a android phone) and two devices (Nordic nRF58240 boards)."
    link: "https://github.com/named-data-iot/ndn-iot-package-over-nordic-sdk/"

---

<!-- Nav bar -->
<ul class="nav nav-pills tabs-iconized" role="tablist">
  <li class="active"><a href="#overview" role="tab" data-toggle="tab">
    Software </a>
  </li>
  {% for item in page.category %}
  <li><a href="#{{ item.id }}" role="tab" data-toggle="tab">
    <!-- <i class="fa {{ item.icon }}"></i> --> {{ item.name }}</a>
  </li>
  {% endfor %}
</ul>
<!-- END Nav bar-->

<!-- Content -->
<div class="tab-content">
  <div class="tab-pane fade in active" id="overview">
    <div class="overview">
      {% for item in page.category %}
        <div class="container">
          <div class="panel panel-default">
            <div class="panel-heading">
              <h4><!-- <i class="fa {{ item.icon }}"></i>  -->
                {{ item.name }}
              </h4>
            </div>
            <div class="panel-body">
              <!-- {% bibliography --file background --query @*[keywords ~= dis-{{ item.id }}] %} -->
              <p>{{ item.intro }}</p>
              {% if item.link != "" %}
                <p><a href = "{{ item.link }}">(read more)</a></p>
              {% endif %}
            </div>
          </div>
        </div>
      {% endfor %}
    </div>
  </div>
  {% for item in page.category %}
  <div class="tab-pane fade" id="{{ item.id }}">
    <p> {{ item.intro }} </p>
    <p>
        {% if item.link != "" %}
          <a align="right" href= "{{ item.link }}"> (read more) </a>
        {% endif %}
    </p>
  </div>
  {% endfor %}
</div>
<!-- END Content -->
