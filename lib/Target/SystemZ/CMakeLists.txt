set(LLVM_TARGET_DEFINITIONS SystemZ.td)

tablegen(LLVM SystemZGenAsmMatcher.inc -gen-asm-matcher)
tablegen(LLVM SystemZGenAsmWriter.inc -gen-asm-writer)
tablegen(LLVM SystemZGenCallingConv.inc -gen-callingconv)
tablegen(LLVM SystemZGenDAGISel.inc -gen-dag-isel)
tablegen(LLVM SystemZGenDisassemblerTables.inc -gen-disassembler)
tablegen(LLVM SystemZGenMCCodeEmitter.inc -gen-emitter)
tablegen(LLVM SystemZGenInstrInfo.inc -gen-instr-info)
tablegen(LLVM SystemZGenRegisterInfo.inc -gen-register-info)
tablegen(LLVM SystemZGenSubtargetInfo.inc -gen-subtarget)
add_public_tablegen_target(SystemZCommonTableGen)

add_llvm_target(SystemZCodeGen
  SystemZAsmPrinter.cpp
  SystemZCallingConv.cpp
  SystemZConstantPoolValue.cpp
  SystemZElimCompare.cpp
  SystemZFrameLowering.cpp
  SystemZISelDAGToDAG.cpp
  SystemZISelLowering.cpp
  SystemZInstrInfo.cpp
  SystemZLDCleanup.cpp
  SystemZLongBranch.cpp
  SystemZMachineFunctionInfo.cpp
  SystemZMCInstLower.cpp
  SystemZRegisterInfo.cpp
  SystemZSelectionDAGInfo.cpp
  SystemZShortenInst.cpp
  SystemZSubtarget.cpp
  SystemZTargetMachine.cpp
  SystemZTargetTransformInfo.cpp
  SystemZTDC.cpp
  )

add_subdirectory(AsmParser)
add_subdirectory(Disassembler)
add_subdirectory(InstPrinter)
add_subdirectory(TargetInfo)
add_subdirectory(MCTargetDesc)
