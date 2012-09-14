linux-opengl-abi-proposal
=========================

Linux OpenGL ABI Proposal

This is a proposal to update the Linux OpenGL ABI in order to:

* Redefine what libraries should exist, and what entry points they
  should each expose, given:

    * The emergence of EGL (both within and without the X Window System).
    * The interest in GLES on the desktop.
    * The optional removal of some GL features in OpenGL 3.1.

* Allow multiple OpenGL implementations to co-exist on the filesystem
  without distribution-specific loader or symlink mechanisms.  This should
  resolve the libGL.so installation collisions that people experience today.

* Allow multiple OpenGL implementations to co-exist within the same
  process.  Different threads could be current to different contexts which
  get dispatched to potentially different OpenGL implementations.

Backwards compatibility should be preserved: existing Linux OpenGL
applications should continue to run after this is implemented.

