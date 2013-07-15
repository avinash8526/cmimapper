cmimapper
=========

Python module to convert scorm.com JSON interaction to CMI format

What this modules does ?
=======================

This module takes i/p a JSON file and gives o/p as a JSON with key replaced by cmi prefix according to SCORM standards.
Currently with scorm.com API, interactions reports are generated in XML format. By using xmltodict (another python mod.)
reports can be converted to JSON but the generated JSON is a nested dictionary which doesn't have any cmi prefix.
Hence this module takes care of this problem. It generates a simple python dictionary with cmi prefix which can be used 
to compare reports.
