# Graph Report - moneyprinter  (2026-08-28)

## Corpus Check
- 65 files · ~139,959 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 956 nodes · 1542 edges · 85 communities (39 shown, 46 thin omitted)
- Extraction: 95% EXTRACTED · 5% INFERRED · 0% AMBIGUOUS · INFERRED: 76 edges (avg confidence: 0.91)
- Token cost: 0 input · 0 output

## Graph Freshness
- Built from commit: `196a1eb9`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- services/video.py
- TestLiteLLMProvider
- config.py
- MaterialInfo
- README-ar.md
- Main.py
- README-en.md
- TaskManager
- README.md
- MemoryState
- services/llm.py
- TestCoverrProvider
- v1/video.py
- VideoParams
- TestSocialMetadata
- UploadPostService
- SubMaker
- voice.py
- v1/llm.py
- TestScriptPromptOptions
- subtitle.py
- TestVoiceService
- tts
- TestElevenLabsVoice
- asgi.py
- schema.py
- HttpException
- azure_tts_v1
- create_subtitle
- _build_subtitle_items_from_edge_cues
- TestWebuiI18n
- TestRuntimeEnvironmentDetection
- TestVideoService
- video_effects.py
- MoneyPrinterTurbo Test Directory
- Security Policy
- TestLiteLLMLiveIntegration
- webui.sh
- .test_preprocess_video_rejects_material_outside_local_videos
- .test_get_bgm_file_accepts_song_directory_filename
- .test_get_bgm_file_accepts_project_relative_song_path
- .test_get_bgm_file_rejects_path_outside_song_directory
- .test_get_ffmpeg_binary_uses_configured_env_path
- .test_get_ffmpeg_binary_falls_back_to_imageio_ffmpeg
- .test_get_effective_video_codec_falls_back_when_encoder_missing
- .test_ffmpeg_encoder_exists_falls_back_when_probe_fails
- .test_write_videofile_falls_back_after_runtime_encoder_failure
- .test_write_videofile_does_not_disable_codec_when_fallback_also_fails
- .test_concat_video_clips_falls_back_after_runtime_encoder_failure
- .test_concat_video_clips_does_not_disable_codec_when_fallback_also_fails
- .test_open_video_clip_quietly_suppresses_moviepy_stdout
- .test_combine_videos_closes_audio_clip_when_duration_read_fails
- .test_combine_videos_handles_none_transition_mode
- .test_combine_videos_keeps_small_duration_safety_margin
- .test_concat_video_clips_limits_output_to_audio_duration
- .test_prioritize_unique_source_clips_uses_each_source_before_reuse
- .test_prioritize_unique_source_clips_keeps_sequential_order
- .test_prioritize_unique_source_clips_prefers_long_primary_clip
- .test_wrap_text
- .test_rounded_subtitle_background_clip_has_transparent_corners
- .test_get_audio_duration_accepts_non_mp3_files
- .test_get_audio_duration_missing_file_returns_zero
- .test_no_voice_alias_none_is_supported_temporarily
- .test_no_voice_duration_estimates_non_ascii_languages
- .test_empty_voice_name_does_not_enable_no_voice_mode
- .test_azure_tts_v1_supports_legacy_edge_tts_without_boundary
- .test_azure_tts_v1_times_out_hanging_stream_sync
- .test_mimo_tts_uses_openai_compatible_audio_response
- .test_chatterbox_voice_helpers
- .test_chatterbox_tts_posts_to_openai_compatible_endpoint
- .test_chatterbox_tts_requires_base_url
- .test_chatterbox_tts_returns_none_on_http_error
- .test_generate_subtitle_keeps_edge_provider_for_gemini_legacy_submaker
- .test_script_split_keeps_thousand_separator_comma
- .test_edge_cue_aggregation_handles_thousand_separator_comma
- .test_script_split_supports_arabic_punctuation
- .test_match_script_line_normalizes_arabic_letter_forms
- .test_create_subtitle_ignores_markdown_separator_lines
- .test_create_subtitle_ignores_markdown_underscore_marks
- moneyprinterturbo

## God Nodes (most connected - your core abstractions)
1. `TestLiteLLMProvider` - 35 edges
2. `TestVoiceService` - 34 edges
3. `TestVideoService` - 30 edges
4. `VideoParams` - 27 edges
5. `tts()` - 21 edges
6. `MaterialInfo` - 20 edges
7. `TaskManager` - 16 edges
8. `HttpException` - 16 edges
9. `VideoAspect` - 16 edges
10. `TestCli` - 15 edges

## Surprising Connections (you probably didn't know these)
- `TestTaskService` --uses--> `MaterialInfo`  [INFERRED]
  test/services/test_task.py → app/models/schema.py
- `TestVideoService` --uses--> `MaterialInfo`  [INFERRED]
  test/services/test_video.py → app/models/schema.py
- `TestScriptPromptOptions` --uses--> `VideoScriptRequest`  [INFERRED]
  test/services/test_llm.py → app/models/schema.py
- `TestSecurityControls` --uses--> `TaskQueueFullError`  [INFERRED]
  test/services/test_video.py → app/controllers/manager/base_manager.py
- `TestSecurityControls` --uses--> `InMemoryTaskManager`  [INFERRED]
  test/services/test_video.py → app/controllers/manager/memory_manager.py

## Import Cycles
- None detected.

## Communities (85 total, 46 thin omitted)

### Community 0 - "services/video.py"
Cohesion: 0.06
Nodes (54): VideoConcatMode, VideoTransitionMode, generate_audio(), generate_final_videos(), generate_script(), generate_terms(), get_video_materials(), Generate audio for the video script. If a custom audio file is provided, it… (+46 more)

### Community 1 - "TestLiteLLMProvider"
Cohesion: 0.05
Nodes (17): 验证 LiteLLM provider 的主路径不依赖真实网络和私有 API key。 这里用 fake module 注入…, 某些 OpenAI-compatible 网关在内容过滤或安全拦截时会返回 HTTP 200，但 `choices[0].message` 为…, 自定义 OpenAI-compatible base_url 可能包含代理网关的 user:pass。 SDK 抛错时常会把 URL…, DashScope chat 模式会把文本放在 `output.choices[0].message.content`。 这里覆盖 issue #966…, 保留旧 DashScope completion 响应结构的兼容路径。, Qwen 空响应应返回可诊断错误，而不是底层 AttributeError。, Qwen chat 响应 choices 为空时应返回明确错误。, AIHubMix 是 OpenAI-compatible 网关。这里用 fake OpenAI client 验证独立 provider… (+9 more)

### Community 2 - "config.py"
Cohesion: 0.05
Nodes (26): _can_resolve_hostname(), _decode_linux_route_gateway(), get_container_default_gateway_ip(), get_default_ollama_base_url(), is_running_in_container(), 返回 Ollama 的默认 OpenAI-compatible base_url。 用户显式配置 `ollama_base_url`…, 判断当前进程是否运行在容器内。 这个判断主要用于 Ollama 默认地址选择： - 普通本机运行时，`localhost` 指向用户机器本身； -…, 读取 Linux 容器里的默认网关 IP。 Docker Desktop 通常提供 `host.docker.internal`，但原生 Linux… (+18 more)

### Community 3 - "MaterialInfo"
Cohesion: 0.08
Nodes (27): MaterialInfo, VideoAspect, download_videos(), _download_videos_by_script_order(), get_api_key(), _get_tls_verify(), Coverr (https://coverr.co) - free HD/4K stock videos, subject to Coverr license…, 按脚本文案顺序下载素材。 默认下载逻辑会把所有关键词的候选素材合并成一个大列表；如果第一个 关键词返回很多结果，最终下载时可能一直消耗这个关键词的素材，后续… (+19 more)

### Community 4 - "README-ar.md"
Cohesion: 0.04
Nodes (46): ① إنشاء بيئة Python افتراضية, ① استنساخ المشروع, ① تشغيل حاوية Docker, ② الوصول إلى واجهة الويب, ② تثبيت ImageMagick, ② تعديل ملف الإعدادات, ③ الوصول إلى واجهة الـ API, ③ تشغيل واجهة الويب 🌐 (+38 more)

### Community 5 - "Main.py"
Cohesion: 0.06
Nodes (26): font_dir(), get_ffmpeg_binary(), get_response(), normalize_script_for_subtitle_matching(), public_dir(), Any, 解析当前进程应该使用的 FFmpeg 可执行文件。 增加原因： 1. 视频编码、静音音频生成、pydub 音频转码都依赖 FFmpeg； 2. Windows…, 清理字幕匹配前的脚本文本。 用户可能手动输入 Markdown 分隔符、标题强调或 `_` 这类格式符号。 这些字符通常不会出现在 TTS/Whisper… (+18 more)

### Community 6 - "README-en.md"
Cohesion: 0.05
Nodes (40): ① Clone the Project, ① Create a Python Virtual Environment, ① Launch the Docker Container, ② Access the Web Interface, ② Launch the Web Interface 🌐, ② Modify the Configuration File, ③ Access the API Interface, ③ Launch the API Service 🚀 (+32 more)

### Community 7 - "TaskManager"
Cohesion: 0.08
Nodes (9): Any, TaskManager, TaskQueueFullError, InMemoryTaskManager, RedisTaskManager, _FakeRequest, endpoint 未显式配置时，任务查询接口不能使用 Host 派生绝对 URL， 也不能把展示 URL 回写到任务状态里，否则不同 Host 查询会污染结果。, 并发数用尽后，等待队列必须有硬上限。这里用 max_concurrent_tasks=0 强制任务进入队列，验证超过 max_queued_tasks… (+1 more)

### Community 8 - "README.md"
Cohesion: 0.05
Nodes (37): ① 克隆代码, ① 创建虚拟环境, ① 启动Docker, ② 修改配置文件（可选，建议启动后也可以在 WebUI 里面配置）, ② 启动Web界面 🌐, ② 访问Web界面, ③ 启动API服务 🚀, ③ 访问API文档 (+29 more)

### Community 9 - "MemoryState"
Cohesion: 0.08
Nodes (10): ABC, BaseState, MemoryState, Convert values written by this application back to common Python types. This…, Redis-backed task state. Trust boundary: Redis is expected to be private to…, RedisState, _FakeRedis, Redis SCAN 分批返回 key 时，分页切片必须按当前批次起始位置计算。 这个用例复现 PR #890 描述的 18 条任务、page_size=10… (+2 more)

### Community 10 - "services/llm.py"
Cohesion: 0.14
Nodes (30): build_script_prompt(), build_social_metadata_prompt(), _clamp_text(), _extract_chat_completion_text(), _extract_qwen_generation_text(), _fallback_social_metadata(), _generate_response(), generate_script() (+22 more)

### Community 11 - "TestCoverrProvider"
Cohesion: 0.06
Nodes (14): download_videos 可能被服务层或测试直接传入字符串模式，而不是 VideoConcatMode 枚举。这里用空搜索词避免真实网络请求，只验证…, 开启按文案顺序匹配素材后，不能让第一个关键词的多个候选先把 音频时长填满。这里模拟两个关键词各有多个候选，验证下载顺序是…, Coverr 视频素材源(spec: 2026-06-09-coverr-video-provider-design.md)。 全部用…, search_videos_coverr 应把每个 hit 转成 MaterialInfo，并把 urls.mp4_download 直接作为…, 与 pexels/pixabay 一致:未显式配置时 TLS 校验默认开启。, 企业自签证书代理场景必须能显式关闭 TLS 校验。, Coverr duration 字段在不同响应里可能是 number 或 string, 两种格式都要接受;低于 minimum_duration 的应被过滤。, 默认路径必须开启 TLS 校验，避免素材 API key 和返回的素材 URL 在公共网络或不可信代理环境中被中间人攻击截获或篡改。 (+6 more)

### Community 12 - "v1/video.py"
Cohesion: 0.16
Nodes (29): create_audio(), create_subtitle(), create_task(), create_video(), delete_video(), download_video(), get_all_tasks(), get_bgm_list() (+21 more)

### Community 13 - "VideoParams"
Cohesion: 0.10
Nodes (13): { "video_subject": "", "video_aspect": "横屏 16:9（西瓜视频）", "voice_name": "女生-晓晓",…, VideoParams, WebUI 新增字幕背景开关和颜色选择器后，所有已有语言都必须包含对应 翻译 key，避免某些语言界面直接显示英文内部 key。, UI 会根据开关向后端传递 False 或颜色字符串。这里验证 schema 仍然 接受这两种值，避免后续依赖或类型调整破坏 WebUI 与合成逻辑的契约。, TextClip 的画布会包含字体行高和 baseline 空白，直接居中画布会让 字幕在背景里看起来偏下。这里用一个假 mask 模拟“可见文字像素…, 中文长句按字符换行时，句号等闭合标点不能独占一行，否则字幕背景 会被一个单独的小点撑高。这里复现大字号中文长句的边界情况。, TestSubtitleBackgroundSettings, skipUnless (+5 more)

### Community 14 - "TestSocialMetadata"
Cohesion: 0.12
Nodes (6): { "video_subject": "A day in Shanghai", "video_script": "", "language": "auto",…, VideoSocialMetadataParams, VideoSocialMetadataRequest, 外部 API 不能接受无限长的脚本和语言参数，否则会直接放大 LLM token 成本。schema 层先拦截，服务层再做内部调用兜底。, language 默认 auto 时，不应该固定成某个国家或语种，而是让模型 跟随视频主题和脚本的语言，扩大 API 适用范围。, TestSocialMetadata

### Community 15 - "UploadPostService"
Cohesion: 0.21
Nodes (9): cross_post_video(), Upload-Post API integration for cross-posting videos to TikTok, Instagram and…, Check the status of an upload request. Args: request_id (str): The request ID…, UploadPostService, _get_all(), _has_key(), _mock_response(), patch (+1 more)

### Community 16 - "SubMaker"
Cohesion: 0.18
Nodes (20): chatterbox_tts(), _configure_pydub_ffmpeg(), elevenlabs_tts(), ensure_file_path_exists(), ensure_legacy_submaker_fields(), gemini_tts(), get_audio_duration(), _get_audio_duration_from_submaker() (+12 more)

### Community 17 - "voice.py"
Cohesion: 0.12
Nodes (17): azure_tts_v2(), get_all_azure_voices(), _get_audio_duration_from_file(), get_chatterbox_voices(), get_gemini_voices(), get_mimo_voices(), get_siliconflow_voices(), is_azure_v2_voice() (+9 more)

### Community 18 - "v1/llm.py"
Cohesion: 0.16
Nodes (15): ping(), Request, new_router(), generate_video_script(), generate_video_social_metadata(), generate_video_terms(), post, Request (+7 more)

### Community 19 - "TestScriptPromptOptions"
Cohesion: 0.11
Nodes (8): 自定义 system prompt 会替换默认脚本规则，但视频主题、语言、段落数 仍由服务层统一追加，避免高级用户漏写必要上下文。, 按文案顺序匹配素材依赖 LLM 返回有序关键词。这里不调用真实模型， 只验证服务层会把“按脚本叙事顺序输出”的约束写入 prompt，避免…, API 请求模型需要限制高级 prompt 参数，避免外部调用绕过 WebUI 传入异常段落数或超长提示词，导致模型成本和结果不可控。, reasoning 模型可能返回 `<think>...</think>`。脚本生成链路必须只保留 最终正文，避免思考过程进入字幕和配音。, 如果模型只返回思考块而没有最终答案，应视为空内容，触发重试或明确错误。, 某些网关可能因为截断只返回未闭合的 `<think>`。这种内容同样不能 进入最终脚本；如果清理后没有正文，就应该按空响应处理。, 高级文案要求只作为附加约束，不替换默认系统提示词。 这样普通用户不配置时仍然走稳定默认规则，高级用户也能细化风格。, TestScriptPromptOptions

### Community 20 - "subtitle.py"
Cohesion: 0.17
Nodes (11): correct(), create(), file_to_subtitles(), levenshtein_distance(), similarity(), generate_subtitle(), Generate subtitle for the video script. If subtitle generation is disabled or…, Whisper fallback 校正阶段也必须忽略 `---` 这类不可发声脚本行。 如果这里继续保留 Markdown 分隔符，`correct()`… (+3 more)

### Community 21 - "TestVoiceService"
Cohesion: 0.12
Nodes (5): 即使 FFmpeg 进程返回成功，也要确认输出文件真实存在且非空。这样可以把 异常收敛在 TTS 阶段，而不是拖到后续视频合成阶段才暴露。, 验证 Gemini TTS 在 edge_tts 7.x 环境下仍会返回项目兼容的字幕结构， 并且可以被 `subtitle_provider=edge`…, 无配音模式不调用任何外部 TTS provider，只生成静音音频作为时间轴占位。 这里 mock FFmpeg，验证请求参数、输出文件和 legacy…, 复现阿拉伯语字幕失败的核心路径：脚本包含 أ/ة 等字母形态，edge cue 返回 ا/ه 等归一化形态时，聚合仍应生成完整字幕，避免回退 Whisper。, TestVoiceService

### Community 22 - "tts"
Cohesion: 0.14
Nodes (15): estimate_no_voice_duration(), generate_silent_audio(), is_chatterbox_voice(), is_elevenlabs_voice(), is_gemini_voice(), is_mimo_voice(), is_no_voice(), is_siliconflow_voice() (+7 more)

### Community 24 - "asgi.py"
Cohesion: 0.21
Nodes (11): exception_handler(), get_application(), Request, Application implementation - ASGI., Initialize FastAPI application. Returns: FastAPI: Application object instance., shutdown_event(), startup_event(), validation_exception_handler() (+3 more)

### Community 25 - "schema.py"
Cohesion: 0.41
Nodes (12): BaseResponse, BgmRetrieveResponse, BgmUploadResponse, _Config, TaskDeletionResponse, TaskQueryResponse, TaskResponse, VideoMaterialRetrieveResponse (+4 more)

### Community 26 - "HttpException"
Cohesion: 0.31
Nodes (8): get_api_key(), get_task_id(), Request, verify_token(), FileNotFoundException, HttpException, Any, Exception

### Community 27 - "azure_tts_v1"
Cohesion: 0.18
Nodes (11): azure_tts_v1(), convert_rate_to_percent(), create_edge_tts_communicate(), get_edge_tts_timeout_seconds(), 按当前已安装的 edge_tts 版本构造 Communicate 对象。 背景： 1. 主线代码已经升级到 edge_tts 7.x，并使用…, 获取 Azure TTS V1 单次流式请求的超时时间。 背景： Edge consumer TTS 在网络不通、服务端限流、voice…, 带总超时地消费 edge_tts 7.x 的同步流。 实现原因： `stream_sync()` 本身是阻塞迭代器，网络层卡住时主线程无法及时恢复。…, 统一消费 edge_tts 的同步流和旧版异步流。 edge_tts 7.x 提供 `stream_sync()`，可以在同步函数里直接迭代；… (+3 more)

### Community 28 - "create_subtitle"
Cohesion: 0.22
Nodes (8): create_subtitle(), _do(), _format_text(), 清理字幕对齐前的脚本文本。 这里不能只在 LLM 生成阶段处理，因为用户也可能手动粘贴脚本，或通过 API 直接传入包含 Markdown 标记的文本。TTS…, 将已经聚合好的字幕段写入到 SRT 文件，并做一次基本可读性验证。 返回值： - `True`：字幕文件成功落盘且可被 moviepy 解析； -…, 优化字幕文件 1. 将字幕文件按照标点符号分割成多行 2. 逐行匹配字幕文件中的文本 3. 生成新的字幕文件, _write_subtitle_items(), skipUnless

### Community 29 - "_build_subtitle_items_from_edge_cues"
Cohesion: 0.22
Nodes (10): _build_subtitle_formatter(), _build_subtitle_items_from_edge_cues(), _build_subtitle_items_from_legacy_submaker(), _match_script_line(), _normalize_arabic(), 返回统一的 SRT 行格式化函数。 这里单独拆成一个小工具，是为了让 edge_tts 7.x 的 cues 路径 和项目原有的 legacy…, 统一阿拉伯语常见字母变体，提升字幕 cue 与脚本行的匹配容错率。 edge-tts 对阿拉伯语可能返回与原脚本不同的字母形态，例如把 أ/إ/آ 归一成…, 尝试把当前累计的字幕文本，与脚本中的某一条标准断句匹配起来。 这里复用了项目原有的“按标点拆脚本，再逐段比对”的思路： 1. 优先精确匹配； 2.… (+2 more)

### Community 30 - "TestWebuiI18n"
Cohesion: 0.31
Nodes (3): _load_translation(), TestWebuiI18n, _TrKeyVisitor

### Community 33 - "video_effects.py"
Cohesion: 0.53
Nodes (5): fadein_transition(), fadeout_transition(), slidein_transition(), slideout_transition(), Clip

### Community 34 - "MoneyPrinterTurbo Test Directory"
Cohesion: 0.33
Nodes (5): Adding New Tests, Directory Structure, MoneyPrinterTurbo Test Directory, Running Tests, Test Resources

### Community 35 - "Security Policy"
Cohesion: 0.40
Nodes (4): Disclosure Expectations, Reporting a Vulnerability, Security Policy, Supported Versions

### Community 37 - "webui.sh"
Cohesion: 0.67
Nodes (3): find_available_port(), PYTHONPATH, webui.sh script

## Knowledge Gaps
- **107 isolated node(s):** `moneyprinterturbo`, `PYTHONPATH`, `Supported Versions`, `Reporting a Vulnerability`, `Disclosure Expectations` (+102 more)
  These have ≤1 connection - possible missing edges or undocumented components.
- **46 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `TestVoiceService` connect `TestVoiceService` to `TestElevenLabsVoice`, `create_subtitle`, `.test_get_audio_duration_accepts_non_mp3_files`, `.test_get_audio_duration_missing_file_returns_zero`, `.test_no_voice_alias_none_is_supported_temporarily`, `.test_no_voice_duration_estimates_non_ascii_languages`, `.test_empty_voice_name_does_not_enable_no_voice_mode`, `.test_azure_tts_v1_supports_legacy_edge_tts_without_boundary`, `.test_azure_tts_v1_times_out_hanging_stream_sync`, `.test_mimo_tts_uses_openai_compatible_audio_response`, `.test_chatterbox_voice_helpers`, `.test_chatterbox_tts_posts_to_openai_compatible_endpoint`, `.test_chatterbox_tts_requires_base_url`, `.test_chatterbox_tts_returns_none_on_http_error`, `.test_generate_subtitle_keeps_edge_provider_for_gemini_legacy_submaker`, `.test_script_split_keeps_thousand_separator_comma`, `.test_edge_cue_aggregation_handles_thousand_separator_comma`, `.test_script_split_supports_arabic_punctuation`, `.test_match_script_line_normalizes_arabic_letter_forms`, `.test_create_subtitle_ignores_markdown_separator_lines`, `.test_create_subtitle_ignores_markdown_underscore_marks`?**
  _High betweenness centrality (0.092) - this node is a cross-community bridge._
- **Why does `TestLiteLLMProvider` connect `TestLiteLLMProvider` to `TestSocialMetadata`?**
  _High betweenness centrality (0.084) - this node is a cross-community bridge._
- **Why does `TestVideoService` connect `TestVideoService` to `MaterialInfo`, `TaskManager`, `.test_preprocess_video_rejects_material_outside_local_videos`, `.test_get_bgm_file_accepts_song_directory_filename`, `.test_get_bgm_file_accepts_project_relative_song_path`, `.test_get_bgm_file_rejects_path_outside_song_directory`, `.test_get_ffmpeg_binary_uses_configured_env_path`, `.test_get_ffmpeg_binary_falls_back_to_imageio_ffmpeg`, `.test_get_effective_video_codec_falls_back_when_encoder_missing`, `.test_ffmpeg_encoder_exists_falls_back_when_probe_fails`, `.test_write_videofile_falls_back_after_runtime_encoder_failure`, `.test_write_videofile_does_not_disable_codec_when_fallback_also_fails`, `.test_concat_video_clips_falls_back_after_runtime_encoder_failure`, `.test_concat_video_clips_does_not_disable_codec_when_fallback_also_fails`, `.test_open_video_clip_quietly_suppresses_moviepy_stdout`, `.test_combine_videos_closes_audio_clip_when_duration_read_fails`, `.test_combine_videos_handles_none_transition_mode`, `.test_combine_videos_keeps_small_duration_safety_margin`, `.test_concat_video_clips_limits_output_to_audio_duration`, `.test_prioritize_unique_source_clips_uses_each_source_before_reuse`, `.test_prioritize_unique_source_clips_keeps_sequential_order`, `.test_prioritize_unique_source_clips_prefers_long_primary_clip`, `.test_wrap_text`, `.test_rounded_subtitle_background_clip_has_transparent_corners`?**
  _High betweenness centrality (0.081) - this node is a cross-community bridge._
- **Are the 5 inferred relationships involving `VideoParams` (e.g. with `RedisTaskManager` and `start()`) actually correct?**
  _`VideoParams` has 5 INFERRED edges - model-reasoned connections that need verification._
- **What connects `moneyprinterturbo`, `PYTHONPATH`, `Supported Versions` to the rest of the system?**
  _107 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `services/video.py` be split into smaller, more focused modules?**
  _Cohesion score 0.06428988895382817 - nodes in this community are weakly interconnected._
- **Should `TestLiteLLMProvider` be split into smaller, more focused modules?**
  _Cohesion score 0.054901960784313725 - nodes in this community are weakly interconnected._