# Copyright 2019-2020 CERN and copyright holders of ALICE O2.
# See https://alice-o2.web.cern.ch/copyright for details of the copyright holders.
# All rights not expressly granted are reserved.
#
# This software is distributed under the terms of the GNU General Public
# License v3 (GPL Version 3), copied verbatim in the file "COPYING".
#
# In applying this license CERN does not waive the privileges and immunities
# granted to it by virtue of its status as an Intergovernmental Organization
# or submit itself to any jurisdiction.

if(FastJet_FOUND)
o2physics_add_library(PWGJECore
               SOURCES  FastJetUtilities.cxx
                        JetFinder.cxx
                        JetBkgSubUtils.cxx
                        emcalCrossTalkEmulation.cxx
               PUBLIC_LINK_LIBRARIES O2Physics::AnalysisCore FastJet::FastJet FastJet::Contrib ONNXRuntime::ONNXRuntime O2::EMCALBase O2::EMCALReconstruction)

o2physics_target_root_dictionary(PWGJECore
              HEADERS JetFinder.h
                      JetUtilities.h
                      FastJetUtilities.h
                      JetTaggingUtilities.h
                      JetBkgSubUtils.h
                      JetDerivedDataUtilities.h
                      emcalCrossTalkEmulation.h
                      utilsTrackMatchingEMC.h
              LINKDEF PWGJECoreLinkDef.h)
endif()
