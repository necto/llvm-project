set(LLVM_LINK_COMPONENTS
  FrontendOpenMP
  Support
  )

add_clang_unittest(StaticAnalysisTests
  AnalyzerOptionsTest.cpp
  APSIntTypeTest.cpp
  BugReportInterestingnessTest.cpp
  CallDescriptionTest.cpp
  CallEventTest.cpp
  ConflictingEvalCallsTest.cpp
  ExprEngineVisitTest.cpp
  FalsePositiveRefutationBRVisitorTest.cpp
  IsCLibraryFunctionTest.cpp
  MemRegionDescriptiveNameTest.cpp
  NoStateChangeFuncVisitorTest.cpp
  ObjcBug-124477.cpp
  ParamRegionTest.cpp
  RangeSetTest.cpp
  RegisterCustomCheckersTest.cpp
  StoreTest.cpp
  SymbolReaperTest.cpp
  SValSimplifyerTest.cpp
  SValTest.cpp
  TestReturnValueUnderConstruction.cpp
  Z3CrosscheckOracleTest.cpp
  )

clang_target_link_libraries(StaticAnalysisTests
  PRIVATE
  clangBasic
  clangAnalysis
  clangAST
  clangASTMatchers
  clangCrossTU
  clangFrontend
  clangSerialization
  clangStaticAnalyzerCore
  clangStaticAnalyzerFrontend
  clangTooling
  )

target_link_libraries(StaticAnalysisTests
  PRIVATE
  clangTesting
  )
