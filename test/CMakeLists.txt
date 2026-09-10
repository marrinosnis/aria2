add_executable(aria2c)


list(APPEND srcs
    AllTest.cc;
	TestUtil.cc; TestUtil.h;
	SocketCoreTest.cc;
	array_funTest.cc;
	Base64Test.cc;
	Base32Test.cc;
	a2functionalTest.cc;
	FileEntryTest.cc;
	PieceTest.cc;
	SegmentTest.cc;
	GrowSegmentTest.cc;
	SingleFileAllocationIteratorTest.cc;
	DefaultBtProgressInfoFileTest.cc;
	RequestGroupTest.cc;
	UtilTest1.cc;
	UtilTest2.cc;
	UtilSecurityTest.cc;
	UriListParserTest.cc;
	HttpHeaderProcessorTest.cc;
	RequestTest.cc;
	HttpRequestTest.cc;
	RequestGroupManTest.cc;
	AuthConfigFactoryTest.cc;
	NetrcAuthResolverTest.cc;
	DefaultAuthResolverTest.cc;
	OptionHandlerTest.cc;
	SegmentManTest.cc;
	BitfieldManTest.cc;
	NetrcTest.cc;
	SingletonHolderTest.cc;
	HttpHeaderTest.cc;
	HttpResponseTest.cc;
	FileTest.cc;
	OptionTest.cc;
	DefaultDiskWriterTest.cc;
	FeatureConfigTest.cc;
	SpeedCalcTest.cc;
	MultiDiskAdaptorTest.cc;
	MultiFileAllocationIteratorTest.cc;
	FixedNumberRandomizer.h;
	ProtocolDetectorTest.cc;
	ExceptionTest.cc;
	FmtTest.cc;
	DownloadHandlersTest.cc;
	SignatureTest.cc;
	ServerStatManTest.cc;
	FeedbackURISelectorTest.cc;
	InorderURISelectorTest.cc;
	ServerStatTest.cc;
	NsCookieParserTest.cc;
	DirectDiskAdaptorTest.cc;
	CookieTest.cc;
	CookieStorageTest.cc;
	TimeTest.cc;
	FtpConnectionTest.cc;
	OptionParserTest.cc;
	DNSCacheTest.cc;
	DownloadHelperTest.cc;
	SequentialPickerTest.cc;
	RarestPieceSelectorTest.cc;
	PieceStatManTest.cc;
	InorderPieceSelector.h;
	LongestSequencePieceSelectorTest.cc;
	a2algoTest.cc;
	bitfieldTest.cc;
	DownloadContextTest.cc;
	SessionSerializerTest.cc;
	ValueBaseTest.cc;
	ChunkedDecodingStreamFilterTest.cc;
	UriTest.cc;
	UriSplitTest.cc;
	MockSegment.h;
	CookieHelperTest.cc;
	JsonTest.cc;
	ValueBaseJsonParserTest.cc;
	RpcResponseTest.cc;
	RpcMethodTest.cc;
	HttpServerTest.cc;
	BufferedFileTest.cc;
	GeomStreamPieceSelectorTest.cc;
	SegListTest.cc;
	ParamedStringTest.cc;
	RpcHelperTest.cc;
	AbstractCommandTest.cc;
	SinkStreamFilterTest.cc;
	WrDiskCacheTest.cc;
	WrDiskCacheEntryTest.cc;
	GroupIdTest.cc;
	IndexedListTest.cc ;
	SimpleRandomizerTest.cc;
)

if(ENABLE_XML_RPC)
    list(APPEND srcs XmlRpcRequestParserControllerTest.cc)
endif()

if(HAVE_SOME_FALLOCATE)
    list(APPEND srcs FallocFileAllocationIteratorTest.cc)
endif()

if(HAVE_ZLIB)
    list(APPEND srcs GZipDecoder.cc GZipDecoder.h GZipDecoderTest.cc GZipEncoderTest.cc GZipDecodingStreamFilterTest.cc GZipFileTest.cc)
endif()

if(HAVE_SQLITE3)
    list(APPEND srcs Sqlite3CookieParserTest.cc)
endif()

list(APPEND MessageDigestHelperTest.cc IteratableChunkChecksumValidatorTest.cc IteratableChecksumValidatorTest.cc MessageDigestTest.cc)

if(ENABLE_BITTORRENT)
    list(APPEND srcs
    BtAllowedFastMessageTest.cc;
	BtBitfieldMessageTest.cc;
	BtCancelMessageTest.cc;
	BtChokeMessageTest.cc;
	BtHandshakeMessageTest.cc;
	BtHaveAllMessageTest.cc;
	BtHaveMessageTest.cc;
	BtHaveNoneMessageTest.cc;
	BtInterestedMessageTest.cc;
	BtKeepAliveMessageTest.cc;
	BtNotInterestedMessageTest.cc;
	BtPieceMessageTest.cc;
	BtPortMessageTest.cc;
	BtRejectMessageTest.cc;
	BtRequestMessageTest.cc;
	BtSuggestPieceMessageTest.cc;
	BtUnchokeMessageTest.cc;
	DefaultPieceStorageTest.cc;
	DefaultBtAnnounceTest.cc;
	DefaultBtMessageDispatcherTest.cc;
	DefaultBtRequestFactoryTest.cc;
	MockBtMessage.h;
	MockBtMessageDispatcher.h;
	MockBtMessageFactory.h;
	AnnounceListTest.cc;
	DefaultPeerStorageTest.cc;
	MockPeerStorage.h;
	ByteArrayDiskWriterTest.cc;
	PeerTest.cc;
	PeerSessionResourceTest.cc;
	ShareRatioSeedCriteriaTest.cc;
	BtRegistryTest.cc;
	BtDependencyTest.cc;
	BtPostDownloadHandlerTest.cc;
	TimeSeedCriteriaTest.cc;
	BtExtendedMessageTest.cc;
	HandshakeExtensionMessageTest.cc;
	UTPexExtensionMessageTest.cc;
	UTMetadataRequestExtensionMessageTest.cc;
	UTMetadataDataExtensionMessageTest.cc;
	UTMetadataRejectExtensionMessageTest.cc;
	UTMetadataRequestTrackerTest.cc;
	UTMetadataRequestFactoryTest.cc;
	UTMetadataPostDownloadHandlerTest.cc;
	MagnetTest.cc;
	DefaultBtMessageFactoryTest.cc;
	DefaultExtensionMessageFactoryTest.cc;
	DHTNodeTest.cc;
	DHTBucketTest.cc;
	DHTRoutingTableTest.cc;
	DHTMessageTrackerEntryTest.cc;
	DHTMessageTrackerTest.cc;
	DHTConnectionImplTest.cc;
	DHTPingMessageTest.cc;
	DHTPingReplyMessageTest.cc;
	DHTFindNodeMessageTest.cc;
	DHTFindNodeReplyMessageTest.cc;
	DHTGetPeersMessageTest.cc;
	DHTGetPeersReplyMessageTest.cc;
	DHTAnnouncePeerMessageTest.cc;
	DHTAnnouncePeerReplyMessageTest.cc;
	DHTUnknownMessageTest.cc;
	DHTMessageFactoryImplTest.cc;
	DHTBucketTreeTest.cc;
	DHTPeerAnnounceEntryTest.cc;
	DHTPeerAnnounceStorageTest.cc;
	DHTTokenTrackerTest.cc;
	XORCloserTest.cc;
	DHTIDCloserTest.cc;
	DHTRoutingTableSerializerTest.cc;
	DHTRoutingTableDeserializerTest.cc;
	DHTTaskExecutorTest.cc;
	DHKeyExchangeTest.cc;
	ARC4Test.cc;
	MSEHandshakeTest.cc;
	MockBtAnnounce.h;
	MockBtProgressInfoFile.h;
	MockBtRequestFactory.h;
	MockDHTMessage.h;
	MockDHTMessageCallback.h;
	MockDHTMessageDispatcher.h;
	MockDHTMessageFactory.h;
	MockDHTTask.h;
	MockDHTTaskFactory.h;
	MockDHTTaskQueue.h;
	MockExtensionMessage.h;
	MockExtensionMessageFactory.h;
	MockPieceStorage.h;
	BittorrentHelperTest.cc;
	PriorityPieceSelectorTest.cc;
	MockPieceSelector.h;
	extension_message_test_helper.h;
	LpdMessageDispatcherTest.cc;
	LpdMessageReceiverTest.cc;
	Bencode2Test.cc;
	PeerConnectionTest.cc;
	ValueBaseBencodeParserTest.cc;
	ExtensionMessageRegistryTest.cc;
	UDPTrackerClientTest.cc
    )
endif()


if(ENABLE_METALINK)
    list(APPEND srcs MetalinkerTest.cc MetalinkEntryTest.cc Metalink2RequestGroupTest.cc MetalinkPostDownloadHandlerTest.cc MetalinkHelperTest.cc MetalinkParserControllerTest.cc MetalinkProcessorTest.cc)
endif()

if(ENABLE_ASYNC_DNS)
    list(APPEND srcs AsyncNameResolverTest.cc)
endif()

if(NOT HAVE_TIMEGM)
    list(APPEND srcs TimegmTest.cc)
endif()

if(ENABLE_LIBARIA2)
    list(APPEND srcs Aria2ApiTest.cc)
endif()

target_link_options(aria2c 
    PRIVATE  
        ../src/libaria2.la
        ${LIBINTL_LIBRARIES}
        ${EXTRALIBS}
        ${ZLIB_LIBS}
        ${LIBUV_LIBRARIES}
        ${LIBXML2_LIBRARIES}
        ${EXPAT_LIBRARIES}
        ${SQLITE3_LIBRARIES}
        ${WINTLS_LIBS}
        ${LIBGNUTLS_LIBRARIES}
        ${OPENSSL_LIBRARIES}
        ${LIBGMP_LIBRARIES}
        ${LIBGCRYPT_LIBRARIES}
        ${LIBSSH2_LIBRARIES}
        ${LIBCARES_LIBRARIES}
        ${WSLAY_LIBRARIES}
        ${CPPUNIT_LIBRARIES}
        ${TCMALLOC_LIBRARIES}
        ${JEMALLOC_LBRARIES}
)

target_include_directories(aria2c 
    PRIVATE
        ${PROJECT_SOURCE_DIR}/src
        ${PROJECT_SOURCE_DIR}/src/includes
        ${PROJECT_SOURCE_DIR}/lib
        ${PROJECT_SOURCE_DIR}/intl
           
        ${PROJECT_BINARY_dir}/src/includes    
    )

string(APPEND CMAKE_CXX_FLAGS " ${CMAKE_CXX_FLAGS} "
)

string(APPEND CMAKE_LD_FLAGS)

string(APPEND CMAKE_C_FLAGS " ${CMAKE_C_FLAGS} ${EXTRACFLAGS}")
string(APPEND CMAKE_CXX_FLAGS " ${CMAKE_CXX_FLAGS} ${WARNCXXFLAGS} ${CXX1CXXFLAGS} ${EXTRACXXFLAGS}") 


target_sources(aria2c 
    PRIVATE


    PUBLIC:
        FILE_SET HEADERS
        BASE_DIRS ${CMAKE_CURRENT_LIST_DIR}
        FILES



)